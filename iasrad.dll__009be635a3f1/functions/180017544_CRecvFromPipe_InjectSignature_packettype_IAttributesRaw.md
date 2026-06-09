# CRecvFromPipe::InjectSignature(_packettype_,IAttributesRaw *)

- ea: `0x180017544`
- end: `0x1800178af`
- name: `?InjectSignature@CRecvFromPipe@@AEAAJW4_packettype_@@PEAUIAttributesRaw@@@Z`
- size: `875`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800179a4`

## callees

- `0x1800094e4`
- `0x180017544`
- `0x18001d31c`
- `0x18002ada0`
- `0x18002af04`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017665`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017665`

## pseudocode

```c
__int64 __fastcall CRecvFromPipe::InjectSignature(__int64 a1, int a2, __int64 *a3)
{
  int v4; // ebx
  _DWORD *v5; // rdi
  __int64 v6; // rdx
  LPVOID v7; // rax
  __int64 v8; // rax
  __int64 v10; // [rsp+28h] [rbp-30h] BYREF
  _QWORD v11[2]; // [rsp+30h] [rbp-28h] BYREF
  __int128 v12; // [rsp+40h] [rbp-18h] BYREF
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF
  _QWORD *v14; // [rsp+78h] [rbp+20h] BYREF

  v13 = a1;
  v4 = 0;
  v5 = 0;
  v14 = 0;
  if ( ((a2 - 2) & 0xFFFFFFF6) != 0 || a2 == 10 )
    goto LABEL_43;
  LODWORD(v13) = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*a3 + 48))(a3, &v13);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to obtain attribute count in request while processing message authenticator attribute in out-bound packet ");
      v6 = 40;
LABEL_42:
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids, "NPSRAD");
      goto LABEL_43;
    }
    goto LABEL_43;
  }
  v4 = IASAttributeAlloc(1, (LPVOID *)&v14);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to allocate IAS attribute for message authenticator while processing out-bound RADIUS packet");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids, "NPSRAD");
    }
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    v5 = v14;
    goto LABEL_43;
  }
  v7 = CoTaskMemAlloc(0x10u);
  v5 = v14;
  v14[4] = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to allocate dynamic memory for message authenticator attribute value while processing out-bound RADIUS packet");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids, "NPSRAD");
    }
    v4 = -2147024882;
    goto LABEL_43;
  }
  v5[2] = 80;
  v5[4] = 6;
  v5[6] = 16;
  v5[1] = 7;
  v11[0] = 0;
  v12 = 0;
  v11[1] = v5;
  v8 = *a3;
  if ( (_DWORD)v13 )
  {
    v10 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v8 + 104))(a3, 0, &v10);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Unable to find first attribute to request while processing out-bound RADIUS packet");
        v6 = 44;
        goto LABEL_42;
      }
      goto LABEL_43;
    }
    *((_QWORD *)&v12 + 1) = v10;
    v4 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, __int128 *))(*a3 + 64))(a3, v11, &v12);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Unable to add message authenticator attribute to request while processing out-bound RADIUS packet");
        v6 = 45;
        goto LABEL_42;
      }
      goto LABEL_43;
    }
LABEL_38:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("message authenticator Attribute added to out-bound RADIUS packet");
      v6 = 46;
      goto LABEL_42;
    }
    goto LABEL_43;
  }
  v4 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD *))(v8 + 24))(a3, 1, v11);
  if ( v4 >= 0 )
    goto LABEL_38;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Unable to add message authenticator attribute to request while processing out-bound RADIUS packet");
    v6 = 43;
    goto LABEL_42;
  }
LABEL_43:
  if ( v5 )
    IASAttributeRelease(v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180017544  mov     r11, rsp
0x180017547  mov     [r11+10h], rbx
0x18001754b  mov     [r11+18h], rsi
0x18001754f  mov     [r11+8], rcx
0x180017553  push    rdi
0x180017554  sub     rsp, 50h
0x180017558  mov     rsi, r8
0x18001755b  xor     ebx, ebx
0x18001755d  xor     edi, edi
0x18001755f  mov     [r11+20h], rdi
0x180017563  lea     eax, [rdx-2]
0x180017566  test    eax, 0FFFFFFF6h
0x18001756b  jnz     loc_180017890
0x180017571  cmp     edx, 0Ah
0x180017574  jz      loc_180017890
0x18001757a  mov     dword ptr [rsp+58h+arg_0], edi
0x18001757e  mov     rax, [r8]
0x180017581  lea     rdx, [r11+8]
0x180017585  mov     rcx, r8
0x180017588  mov     rax, [rax+30h]
0x18001758c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017591  mov     ebx, eax
0x180017593  mov     [rsp+58h+var_38], eax
0x180017597  test    eax, eax
0x180017599  jns     short loc_1800175DD
0x18001759b  lea     rax, WPP_GLOBAL_Control
0x1800175a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800175a9  cmp     rcx, rax
0x1800175ac  jz      loc_180017890
0x1800175b2  cmp     byte ptr [rcx+19h], 2
0x1800175b6  jb      loc_180017890
0x1800175bc  test    dword ptr [rcx+1Ch], 100h
0x1800175c3  jz      loc_180017890
0x1800175c9  lea     rcx, aUnableToObtain_12; "Unable to obtain attribute count in req"...
0x1800175d0  call    WppDbgPrint
0x1800175d5  lea     edx, [rdi+28h]
0x1800175d8  jmp     loc_180017871
0x1800175dd  lea     rdx, [rsp+58h+arg_18]
0x1800175e2  mov     ecx, 1
0x1800175e7  call    IASAttributeAlloc
0x1800175ec  mov     ebx, eax
0x1800175ee  test    eax, eax
0x1800175f0  jz      short loc_18001765E
0x1800175f2  lea     rax, WPP_GLOBAL_Control
0x1800175f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180017600  cmp     rcx, rax
0x180017603  jz      short loc_180017643
0x180017605  cmp     byte ptr [rcx+19h], 2
0x180017609  jb      short loc_180017643
0x18001760b  test    dword ptr [rcx+1Ch], 100h
0x180017612  jz      short loc_180017643
0x180017614  lea     rcx, aUnableToAlloca_14; "Unable to allocate IAS attribute for me"...
0x18001761b  call    WppDbgPrint
0x180017620  mov     edx, 29h ; ')'
0x180017625  lea     r9, aNpsrad; "NPSRAD"
0x18001762c  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x180017633  mov     rcx, cs:WPP_GLOBAL_Control
0x18001763a  mov     rcx, [rcx+10h]
0x18001763e  call    WPP_SF_s
0x180017643  test    ebx, ebx
0x180017645  jle     short loc_180017650
0x180017647  movzx   ebx, bx
0x18001764a  or      ebx, 80070000h
0x180017650  mov     [rsp+58h+var_38], ebx
0x180017654  mov     rdi, [rsp+58h+arg_18]
0x180017659  jmp     loc_180017890
0x18001765e  mov     ebx, 10h
0x180017663  mov     ecx, ebx; cb
0x180017665  call    cs:__imp_CoTaskMemAlloc
0x18001766b  mov     rdi, [rsp+58h+arg_18]
0x180017670  mov     [rdi+20h], rax
0x180017674  test    rax, rax
0x180017677  jnz     short loc_1800176D6
0x180017679  lea     rax, WPP_GLOBAL_Control
0x180017680  mov     rcx, cs:WPP_GLOBAL_Control
0x180017687  cmp     rcx, rax
0x18001768a  jz      short loc_1800176C8
0x18001768c  cmp     byte ptr [rcx+19h], 2
0x180017690  jb      short loc_1800176C8
0x180017692  test    dword ptr [rcx+1Ch], 100h
0x180017699  jz      short loc_1800176C8
0x18001769b  lea     rcx, aUnableToAlloca_10; "Unable to allocate dynamic memory for m"...
0x1800176a2  call    WppDbgPrint
0x1800176a7  lea     edx, [rbx+1Ah]
0x1800176aa  lea     r9, aNpsrad; "NPSRAD"
0x1800176b1  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x1800176b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800176bf  mov     rcx, [rcx+10h]
0x1800176c3  call    WPP_SF_s
0x1800176c8  mov     ebx, 8007000Eh
0x1800176cd  mov     [rsp+58h+var_38], ebx
0x1800176d1  jmp     loc_180017890
0x1800176d6  mov     dword ptr [rdi+8], 50h ; 'P'
0x1800176dd  mov     dword ptr [rdi+10h], 6
0x1800176e4  mov     [rdi+18h], ebx
0x1800176e7  mov     dword ptr [rdi+4], 7
0x1800176ee  xorps   xmm0, xmm0
0x1800176f1  movups  [rsp+58h+var_28], xmm0
0x1800176f6  xorps   xmm1, xmm1
0x1800176f9  movups  [rsp+58h+var_18], xmm1
0x1800176fe  mov     qword ptr [rsp+58h+var_28+8], rdi
0x180017703  mov     rax, [rsi]
0x180017706  mov     rcx, rsi
0x180017709  cmp     dword ptr [rsp+58h+arg_0], 0
0x18001770e  jnz     short loc_180017775
0x180017710  lea     r8, [rsp+58h+var_28]
0x180017715  mov     edx, 1
0x18001771a  mov     rax, [rax+18h]
0x18001771e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017723  mov     ebx, eax
0x180017725  mov     [rsp+58h+var_38], eax
0x180017729  test    eax, eax
0x18001772b  jns     loc_18001783E
0x180017731  lea     rax, WPP_GLOBAL_Control
0x180017738  mov     rcx, cs:WPP_GLOBAL_Control
0x18001773f  cmp     rcx, rax
0x180017742  jz      loc_180017890
0x180017748  cmp     byte ptr [rcx+19h], 2
0x18001774c  jb      loc_180017890
0x180017752  test    dword ptr [rcx+1Ch], 100h
0x180017759  jz      loc_180017890
0x18001775f  lea     rcx, aUnableToAddMes; "Unable to add message authenticator att"...
0x180017766  call    WppDbgPrint
0x18001776b  mov     edx, 2Bh ; '+'
0x180017770  jmp     loc_180017871
0x180017775  mov     [rsp+58h+var_30], 0
0x18001777e  lea     r8, [rsp+58h+var_30]
0x180017783  xor     edx, edx
0x180017785  mov     rax, [rax+68h]
0x180017789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001778e  mov     ebx, eax
0x180017790  mov     [rsp+58h+var_38], eax
0x180017794  test    eax, eax
0x180017796  jns     short loc_1800177DC
0x180017798  lea     rax, WPP_GLOBAL_Control
0x18001779f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177a6  cmp     rcx, rax
0x1800177a9  jz      loc_180017890
0x1800177af  cmp     byte ptr [rcx+19h], 2
0x1800177b3  jb      loc_180017890
0x1800177b9  test    dword ptr [rcx+1Ch], 100h
0x1800177c0  jz      loc_180017890
0x1800177c6  lea     rcx, aUnableToFindFi; "Unable to find first attribute to reque"...
0x1800177cd  call    WppDbgPrint
0x1800177d2  mov     edx, 2Ch ; ','
0x1800177d7  jmp     loc_180017871
0x1800177dc  mov     rax, [rsp+58h+var_30]
0x1800177e1  mov     qword ptr [rsp+58h+var_18+8], rax
0x1800177e6  mov     rax, [rsi]
0x1800177e9  lea     r8, [rsp+58h+var_18]
0x1800177ee  lea     rdx, [rsp+58h+var_28]
0x1800177f3  mov     rcx, rsi
0x1800177f6  mov     rax, [rax+40h]
0x1800177fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177ff  mov     ebx, eax
0x180017801  mov     [rsp+58h+var_38], eax
0x180017805  test    eax, eax
0x180017807  jns     short loc_18001783E
0x180017809  lea     rax, WPP_GLOBAL_Control
0x180017810  mov     rcx, cs:WPP_GLOBAL_Control
0x180017817  cmp     rcx, rax
0x18001781a  jz      short loc_180017890
0x18001781c  cmp     byte ptr [rcx+19h], 2
0x180017820  jb      short loc_180017890
0x180017822  test    dword ptr [rcx+1Ch], 100h
0x180017829  jz      short loc_180017890
0x18001782b  lea     rcx, aUnableToAddMes; "Unable to add message authenticator att"...
0x180017832  call    WppDbgPrint
0x180017837  mov     edx, 2Dh ; '-'
0x18001783c  jmp     short loc_180017871
0x18001783e  lea     rax, WPP_GLOBAL_Control
0x180017845  mov     rcx, cs:WPP_GLOBAL_Control
0x18001784c  cmp     rcx, rax
0x18001784f  jz      short loc_180017890
0x180017851  cmp     byte ptr [rcx+19h], 4
0x180017855  jb      short loc_180017890
0x180017857  test    dword ptr [rcx+1Ch], 100h
0x18001785e  jz      short loc_180017890
0x180017860  lea     rcx, aMessageAuthent_2; "message authenticator Attribute added t"...
0x180017867  call    WppDbgPrint
0x18001786c  mov     edx, 2Eh ; '.'
0x180017871  mov     rcx, cs:WPP_GLOBAL_Control
0x180017878  lea     r9, aNpsrad; "NPSRAD"
0x18001787f  lea     r8, WPP_ed9712b053c33f492fa08cace3005bc4_Traceguids
0x180017886  mov     rcx, [rcx+10h]
0x18001788a  call    WPP_SF_s
0x18001788f  nop
0x180017890  test    rdi, rdi
0x180017893  jz      short loc_18001789D
0x180017895  mov     rcx, rdi; pv
0x180017898  call    IASAttributeRelease
0x18001789d  mov     eax, ebx
0x18001789f  mov     rbx, [rsp+58h+arg_8]
0x1800178a4  mov     rsi, [rsp+58h+arg_10]
0x1800178a9  add     rsp, 50h
0x1800178ad  pop     rdi
0x1800178ae  retn
0x18002ed71  push    rbp
0x18002ed73  sub     rsp, 20h
0x18002ed77  mov     rbp, rdx
0x18002ed7a  mov     rcx, [rbp+78h]; pv
0x18002ed7e  test    rcx, rcx
0x18002ed81  jz      short loc_18002ED89
0x18002ed83  call    IASAttributeRelease
0x18002ed88  nop
0x18002ed89  add     rsp, 20h
0x18002ed8d  pop     rbp
0x18002ed8e  retn
```
