# IfObjectConnectedEx(void *,void *,_PROTOCOL_PROJECTION_RESULT *,RasObjPtr<DdmConnection>,int)

- ea: `0x180008b3c`
- end: `0x180008cd0`
- name: `?IfObjectConnectedEx@@YAKPEAX0PEAU_PROTOCOL_PROJECTION_RESULT@@V?$RasObjPtr@VDdmConnection@@@@H@Z`
- size: `404`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000f254`
- `0x180038560`
- `0x180043490`

## callees

- `0x180007c0c`
- `0x180008a6c`
- `0x180008b3c`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180008c80`
- `KERNEL32!HeapFree` at `0x180008c80`
- `rasman!RasSendNotification` at `0x180008bef`
- `rasman!RasSendNotification` at `0x180008bef`

## string_xrefs

- `0x180008c0c`: `RasSendNotification(INCOMING_CONNECTED) rc=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IfObjectConnectedEx(__int64 a1, __int64 a2, __int64 a3, __int64 *a4, int a5)
{
  __int64 v7; // rax
  _DWORD *v8; // rax
  void *v9; // rbx
  unsigned int v10; // eax
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rcx
  _QWORD v15[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+40h] [rbp-C0h] BYREF
  int *v17; // [rsp+50h] [rbp-B0h]
  int v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+5Ch] [rbp-A4h]
  int v20; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v15[1] = a4;
  (*(void (__fastcall **)(__int64, __int64, __int64, __int64, bool))(*(_QWORD *)g_pIDimInterfaceTable + 104LL))(
    g_pIDimInterfaceTable,
    a1,
    a2,
    a3,
    a5 != 0);
  if ( !dword_1800CF654 )
  {
    v20 = 0;
    memset_0(v21, 0, sizeof(v21));
    v7 = *a4;
    v15[0] = v7;
    if ( v7 )
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
    v8 = (_DWORD *)DDMGetRasEvent(a2, v15);
    v9 = v8;
    if ( v8 )
    {
      *v8 = 0x8000;
      v10 = RasSendNotification(v8);
      if ( (byte_1800CF404 & 0x10) != 0 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"RasSendNotification(INCOMING_CONNECTED) rc=0x%x", v10);
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          v12 = -1;
          do
            ++v12;
          while ( *(_WORD *)&v21[2 * v12 - 4] );
          v17 = &v20;
          v18 = 2 * v12 + 2;
          v19 = 0;
          McGenEventWrite_EventWriteTransfer(
            (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
            v11,
            2u,
            &v16);
        }
      }
      HeapFree(hHeap, 0, v9);
    }
  }
  v13 = *a4;
  if ( *a4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v13)(v13, 1);
  return 0;
}

```

## disassembly

```asm
0x180008b3c  push    rbp
0x180008b3e  push    rbx
0x180008b3f  push    rsi
0x180008b40  push    rdi
0x180008b41  lea     rbp, [rsp-778h]
0x180008b49  sub     rsp, 878h
0x180008b50  mov     rax, cs:__security_cookie
0x180008b57  xor     rax, rsp
0x180008b5a  mov     [rbp+790h+var_30], rax
0x180008b61  mov     rdi, r9
0x180008b64  mov     rbx, rdx
0x180008b67  mov     rdx, rcx
0x180008b6a  mov     [rsp+890h+var_858], r9
0x180008b6f  mov     r10, cs:g_pIDimInterfaceTable
0x180008b76  mov     rax, [r10]
0x180008b79  xor     esi, esi
0x180008b7b  cmp     [rbp+790h+arg_20], esi
0x180008b81  setnz   cl
0x180008b84  mov     byte ptr [rsp+890h+var_870], cl
0x180008b88  mov     r9, r8
0x180008b8b  mov     r8, rbx
0x180008b8e  mov     rcx, r10
0x180008b91  mov     rax, [rax+68h]
0x180008b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b9a  cmp     cs:dword_1800CF654, esi
0x180008ba0  jnz     loc_180008C8D
0x180008ba6  mov     [rsp+890h+var_830], esi
0x180008baa  xor     edx, edx; Val
0x180008bac  mov     r8d, 7FCh; Size
0x180008bb2  lea     rcx, [rsp+890h+var_82C]; void *
0x180008bb7  call    memset_0
0x180008bbc  mov     rax, [rdi]
0x180008bbf  mov     [rsp+890h+var_860], rax
0x180008bc4  test    rax, rax
0x180008bc7  jz      short loc_180008BCD
0x180008bc9  lock inc dword ptr [rax+8]
0x180008bcd  lea     rdx, [rsp+890h+var_860]
0x180008bd2  mov     rcx, rbx
0x180008bd5  call    ?DDMGetRasEvent@@YAPEAU_RASEVENT@@PEAXV?$RasObjPtr@VDdmConnection@@@@@Z; DDMGetRasEvent(void *,RasObjPtr<DdmConnection>)
0x180008bda  mov     rbx, rax
0x180008bdd  test    rax, rax
0x180008be0  jz      loc_180008C8D
0x180008be6  mov     dword ptr [rax], 8000h
0x180008bec  mov     rcx, rax
0x180008bef  call    cs:__imp_RasSendNotification
0x180008bf6  nop     dword ptr [rax+rax+00h]
0x180008bfb  test    cs:byte_1800CF404, 10h
0x180008c02  jz      short loc_180008C74
0x180008c04  mov     word ptr [rsp+890h+var_830], si
0x180008c09  mov     r8d, eax
0x180008c0c  lea     rdx, aRassendnotific; "RasSendNotification(INCOMING_CONNECTED)"...
0x180008c13  lea     rcx, [rsp+890h+var_830]
0x180008c18  call    FormatRRASErrorString
0x180008c1d  test    cs:byte_1800CF404, 10h
0x180008c24  jz      short loc_180008C74
0x180008c26  lea     rcx, [rsp+890h+var_830]
0x180008c2b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008c2f  inc     rax
0x180008c32  cmp     [rcx+rax*2], si
0x180008c36  jnz     short loc_180008C2F
0x180008c38  lea     eax, ds:2[rax*2]
0x180008c3f  lea     rcx, [rsp+890h+var_830]
0x180008c44  mov     [rsp+890h+var_840], rcx
0x180008c49  mov     [rsp+890h+var_838], eax
0x180008c4d  mov     [rsp+890h+var_834], esi
0x180008c51  lea     rax, [rsp+890h+var_850]
0x180008c56  mov     [rsp+890h+var_870], rax
0x180008c5b  mov     r9d, 2
0x180008c61  lea     rdx, RasDdmTraceInfo
0x180008c68  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008c6f  call    McGenEventWrite_EventWriteTransfer
0x180008c74  mov     r8, rbx; lpMem
0x180008c77  xor     edx, edx; dwFlags
0x180008c79  mov     rcx, cs:hHeap; hHeap
0x180008c80  call    cs:__imp_HeapFree
0x180008c87  nop     dword ptr [rax+rax+00h]
0x180008c8c  nop
0x180008c8d  mov     rcx, [rdi]
0x180008c90  test    rcx, rcx
0x180008c93  jz      short loc_180008CB2
0x180008c95  or      eax, 0FFFFFFFFh
0x180008c98  lock xadd [rcx+8], eax
0x180008c9d  cmp     eax, 1
0x180008ca0  jnz     short loc_180008CB2
0x180008ca2  mov     rax, [rcx]
0x180008ca5  mov     edx, 1
0x180008caa  mov     rax, [rax]
0x180008cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cb2  xor     eax, eax
0x180008cb4  mov     rcx, [rbp+790h+var_30]
0x180008cbb  xor     rcx, rsp; StackCookie
0x180008cbe  call    __security_check_cookie
0x180008cc3  add     rsp, 878h
0x180008cca  pop     rdi
0x180008ccb  pop     rsi
0x180008ccc  pop     rbx
0x180008ccd  pop     rbp
0x180008cce  retn
```
