# CRehydrationTaskHandler::Start(IUnknown *,ushort *)

- ea: `0x180008600`
- end: `0x180008794`
- name: `?Start@CRehydrationTaskHandler@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `404`
- prototype: `__int64 __fastcall(_QWORD *pv, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005ea4`
- `0x180005f58`
- `0x1800067a0`
- `0x180008600`
- `0x18000b010`

## import_xrefs

- `KERNEL32!SubmitThreadpoolWork` at `0x180008780`
- `KERNEL32!SubmitThreadpoolWork` at `0x180008780`
- `KERNEL32!CreateThreadpoolWork` at `0x180008717`
- `KERNEL32!CreateThreadpoolWork` at `0x180008717`
- `KERNEL32!GetLastError` at `0x18000869b`
- `KERNEL32!GetLastError` at `0x180008722`
- `KERNEL32!GetLastError` at `0x18000869b`
- `KERNEL32!GetLastError` at `0x180008722`
- `KERNEL32!CreateEventW` at `0x18000868c`
- `KERNEL32!CreateEventW` at `0x18000868c`

## pseudocode

```c
__int64 __fastcall CRehydrationTaskHandler::Start(_QWORD *pv, struct IUnknown *a2, unsigned __int16 *a3)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx
  _BYTE *v8; // rcx
  __int64 v9; // rdx
  struct _TP_WORK *ThreadpoolWork; // rax
  signed int v11; // eax
  struct IUnknown *v13; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids);
  v13 = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IUnknown *, struct IUnknown *, unsigned __int16 *))a2->lpVtbl->AddRef)(a2, a2, a3);
  ATL::CComPtr<ITaskHandlerStatus>::operator=<IUnknown>(pv + 8, &v13, a3);
  if ( a2 )
    ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->Release)(a2);
  EventW = CreateEventW(0, 1, 0, 0);
  pv[10] = EventW;
  if ( EventW )
    goto LABEL_19;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids, v7);
    v8 = WPP_GLOBAL_Control;
  }
  if ( (v7 & 0x80000000) == 0 )
  {
LABEL_19:
    ThreadpoolWork = CreateThreadpoolWork(CRehydrationTaskHandler::s_ThreadWorkCallback, pv, 0);
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      return 0;
    }
    v11 = GetLastError();
    v7 = v11;
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids, v7);
      v8 = WPP_GLOBAL_Control;
    }
    if ( (v7 & 0x80000000) != 0 && v8 != (_BYTE *)&WPP_GLOBAL_Control && (v8[28] & 1) != 0 )
    {
      v9 = 59;
      goto LABEL_18;
    }
  }
  else if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && (v8[28] & 1) != 0 )
  {
    v9 = 58;
LABEL_18:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids, v7);
  }
  return v7;
}

```

## disassembly

```asm
0x180008600  push    rbx
0x180008602  push    rbp
0x180008603  push    rdi
0x180008604  push    r14
0x180008606  sub     rsp, 28h
0x18000860a  mov     rbx, rdx
0x18000860d  mov     rdi, rcx
0x180008610  lea     rbp, WPP_GLOBAL_Control
0x180008617  lea     r14, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x18000861e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008625  cmp     rcx, rbp
0x180008628  jz      short loc_180008642
0x18000862a  test    byte ptr [rcx+1Ch], 8
0x18000862e  jz      short loc_180008642
0x180008630  mov     edx, 39h ; '9'
0x180008635  mov     r8, r14
0x180008638  mov     rcx, [rcx+10h]
0x18000863c  call    WPP_SF_
0x180008641  nop
0x180008642  mov     [rsp+48h+arg_0], rbx
0x180008647  test    rbx, rbx
0x18000864a  jz      short loc_18000865C
0x18000864c  mov     rax, [rbx]
0x18000864f  mov     rcx, rbx
0x180008652  mov     rax, [rax+8]
0x180008656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000865b  nop
0x18000865c  lea     rcx, [rdi+40h]
0x180008660  lea     rdx, [rsp+48h+arg_0]
0x180008665  call    ??$?4UIUnknown@@@?$CComPtr@UITaskHandlerStatus@@@ATL@@QEAAPEAUITaskHandlerStatus@@AEBV?$CComPtr@UIUnknown@@@1@@Z; ATL::CComPtr<ITaskHandlerStatus>::operator=<IUnknown>(ATL::CComPtr<IUnknown> const &)
0x18000866a  nop
0x18000866b  test    rbx, rbx
0x18000866e  jz      short loc_180008680
0x180008670  mov     rax, [rbx]
0x180008673  mov     rcx, rbx
0x180008676  mov     rax, [rax+10h]
0x18000867a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000867f  nop
0x180008680  xor     r9d, r9d; lpName
0x180008683  xor     r8d, r8d; bInitialState
0x180008686  lea     edx, [r9+1]; bManualReset
0x18000868a  xor     ecx, ecx; lpEventAttributes
0x18000868c  call    cs:__imp_CreateEventW
0x180008692  mov     [rdi+50h], rax
0x180008696  test    rax, rax
0x180008699  jnz     short loc_18000870A
0x18000869b  call    cs:__imp_GetLastError
0x1800086a1  mov     ebx, eax
0x1800086a3  test    eax, eax
0x1800086a5  jle     short loc_1800086B0
0x1800086a7  movzx   ebx, ax
0x1800086aa  or      ebx, 80070000h
0x1800086b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086b7  cmp     rcx, rbp
0x1800086ba  jz      short loc_1800086DD
0x1800086bc  test    byte ptr [rcx+1Ch], 1
0x1800086c0  jz      short loc_1800086DD
0x1800086c2  mov     edx, 3Dh ; '='
0x1800086c7  mov     r9d, ebx
0x1800086ca  mov     r8, r14
0x1800086cd  mov     rcx, [rcx+10h]
0x1800086d1  call    WPP_SF_d
0x1800086d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086dd  test    ebx, ebx
0x1800086df  jns     short loc_18000870A
0x1800086e1  cmp     rcx, rbp
0x1800086e4  jz      loc_180008788
0x1800086ea  test    byte ptr [rcx+1Ch], 1
0x1800086ee  jz      loc_180008788
0x1800086f4  mov     edx, 3Ah ; ':'
0x1800086f9  mov     r9d, ebx
0x1800086fc  mov     r8, r14
0x1800086ff  mov     rcx, [rcx+10h]
0x180008703  call    WPP_SF_d
0x180008708  jmp     short loc_180008788
0x18000870a  xor     r8d, r8d; pcbe
0x18000870d  mov     rdx, rdi; pv
0x180008710  lea     rcx, ?s_ThreadWorkCallback@CRehydrationTaskHandler@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180008717  call    cs:__imp_CreateThreadpoolWork
0x18000871d  test    rax, rax
0x180008720  jnz     short loc_18000877D
0x180008722  call    cs:__imp_GetLastError
0x180008728  mov     ebx, eax
0x18000872a  test    eax, eax
0x18000872c  jle     short loc_180008737
0x18000872e  movzx   ebx, ax
0x180008731  or      ebx, 80070000h
0x180008737  mov     rcx, cs:WPP_GLOBAL_Control
0x18000873e  cmp     rcx, rbp
0x180008741  jz      short loc_180008764
0x180008743  test    byte ptr [rcx+1Ch], 1
0x180008747  jz      short loc_180008764
0x180008749  mov     edx, 3Eh ; '>'
0x18000874e  mov     r9d, ebx
0x180008751  mov     r8, r14
0x180008754  mov     rcx, [rcx+10h]
0x180008758  call    WPP_SF_d
0x18000875d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008764  test    ebx, ebx
0x180008766  jns     short loc_180008788
0x180008768  cmp     rcx, rbp
0x18000876b  jz      short loc_180008788
0x18000876d  test    byte ptr [rcx+1Ch], 1
0x180008771  jz      short loc_180008788
0x180008773  mov     edx, 3Bh ; ';'
0x180008778  jmp     loc_1800086F9
0x18000877d  mov     rcx, rax; pwk
0x180008780  call    cs:__imp_SubmitThreadpoolWork
0x180008786  xor     ebx, ebx
0x180008788  mov     eax, ebx
0x18000878a  add     rsp, 28h
0x18000878e  pop     r14
0x180008790  pop     rdi
0x180008791  pop     rbp
0x180008792  pop     rbx
0x180008793  retn
```
