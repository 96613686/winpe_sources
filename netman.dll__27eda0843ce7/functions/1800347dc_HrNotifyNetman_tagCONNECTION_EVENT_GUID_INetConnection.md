# HrNotifyNetman(tagCONNECTION_EVENT,_GUID *,INetConnection *)

- ea: `0x1800347dc`
- end: `0x18003497b`
- name: `?HrNotifyNetman@@YAJW4tagCONNECTION_EVENT@@PEAU_GUID@@PEAUINetConnection@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800273b0`
- `0x1800277d0`
- `0x180029950`
- `0x180029ab0`

## callees

- `0x180001710`
- `0x18000538c`
- `0x1800347dc`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003482c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003482c`

## pseudocode

```c
__int64 __fastcall HrNotifyNetman(int a1, __int64 a2, __int64 a3)
{
  HRESULT v6; // edi
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  __int64 v11; // r8
  HRESULT v12; // eax
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-10h] BYREF

  ppv = 0;
  v6 = CoCreateInstance(&CLSID_ConnectionManager, 0, 0x15u, &GUID_faedcf5f_31fe_11d1_aad2_00805fc1270e, &ppv);
  if ( v6 >= 0 )
  {
    if ( a1 > 6 )
    {
      v13 = a1 - 7;
      if ( !v13 )
      {
        v11 = 3;
        goto LABEL_26;
      }
      v14 = v13 - 1;
      if ( !v14 )
        goto LABEL_23;
      v15 = v14 - 1;
      if ( !v15 )
      {
        v12 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 56LL))(ppv, a3);
        goto LABEL_27;
      }
      v16 = v15 - 1;
      if ( v16 )
      {
        if ( v16 != 1 )
          goto LABEL_21;
        v12 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 24LL))(ppv);
      }
      else
      {
LABEL_23:
        v12 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 48LL))(ppv, a3);
      }
    }
    else
    {
      if ( a1 == 6 )
      {
        v11 = 1;
        goto LABEL_26;
      }
      v7 = a1 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( !v8 )
        {
          v12 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 40LL))(ppv, a2);
          goto LABEL_27;
        }
        v9 = v8 - 1;
        if ( !v9 )
        {
          v11 = 0;
          goto LABEL_26;
        }
        v10 = v9 - 1;
        if ( !v10 )
        {
          v11 = 2;
          goto LABEL_26;
        }
        if ( v10 == 1 )
        {
          v11 = 7;
LABEL_26:
          v12 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 64LL))(ppv, a2, v11);
          goto LABEL_27;
        }
LABEL_21:
        v6 = -2147418113;
LABEL_28:
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        goto LABEL_29;
      }
      v12 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 32LL))(ppv, a3);
    }
LABEL_27:
    v6 = v12;
    goto LABEL_28;
  }
LABEL_29:
  if ( v6 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_127a71f7b91d3825fada0ff6fce676d2_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800347dc  mov     [rsp-18h+arg_0], rbx
0x1800347e1  mov     [rsp-18h+arg_18], rsi
0x1800347e6  push    rbp
0x1800347e7  push    rdi
0x1800347e8  push    r14
0x1800347ea  mov     rbp, rsp
0x1800347ed  sub     rsp, 40h
0x1800347f1  mov     rax, cs:__security_cookie
0x1800347f8  xor     rax, rsp
0x1800347fb  mov     [rbp+var_8], rax
0x1800347ff  mov     rsi, rdx
0x180034802  mov     [rbp+var_10], 0
0x18003480a  xor     edx, edx; pUnkOuter
0x18003480c  lea     rax, [rbp+var_10]
0x180034810  mov     r14, r8
0x180034813  mov     [rsp+40h+ppv], rax; ppv
0x180034818  mov     ebx, ecx
0x18003481a  lea     r9, _GUID_faedcf5f_31fe_11d1_aad2_00805fc1270e; riid
0x180034821  lea     rcx, CLSID_ConnectionManager; rclsid
0x180034828  lea     r8d, [rdx+15h]; dwClsContext
0x18003482c  call    cs:__imp_CoCreateInstance
0x180034832  mov     edi, eax
0x180034834  test    eax, eax
0x180034836  js      loc_180034925
0x18003483c  cmp     ebx, 6
0x18003483f  jg      short loc_1800348A8
0x180034841  jz      short loc_1800348A0
0x180034843  sub     ebx, 1
0x180034846  jz      short loc_180034890
0x180034848  sub     ebx, 1
0x18003484b  jz      short loc_180034878
0x18003484d  sub     ebx, 1
0x180034850  jz      short loc_180034870
0x180034852  sub     ebx, 1
0x180034855  jz      short loc_180034865
0x180034857  cmp     ebx, 1
0x18003485a  jnz     short loc_1800348C1
0x18003485c  lea     r8d, [rbx+6]
0x180034860  jmp     loc_180034900
0x180034865  mov     r8d, 2
0x18003486b  jmp     loc_180034900
0x180034870  xor     r8d, r8d
0x180034873  jmp     loc_180034900
0x180034878  mov     rcx, [rbp+var_10]
0x18003487c  mov     rdx, rsi
0x18003487f  mov     rax, [rcx]
0x180034882  mov     rax, [rax+28h]
0x180034886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003488b  jmp     loc_180034913
0x180034890  mov     rcx, [rbp+var_10]
0x180034894  mov     rdx, r14
0x180034897  mov     rax, [rcx]
0x18003489a  mov     rax, [rax+20h]
0x18003489e  jmp     short loc_180034886
0x1800348a0  mov     r8d, 1
0x1800348a6  jmp     short loc_180034900
0x1800348a8  sub     ebx, 7
0x1800348ab  jz      short loc_1800348FA
0x1800348ad  sub     ebx, 1
0x1800348b0  jz      short loc_1800348DA
0x1800348b2  sub     ebx, 1
0x1800348b5  jz      short loc_1800348EA
0x1800348b7  sub     ebx, 1
0x1800348ba  jz      short loc_1800348DA
0x1800348bc  cmp     ebx, 1
0x1800348bf  jz      short loc_1800348C8
0x1800348c1  mov     edi, 8000FFFFh
0x1800348c6  jmp     short loc_180034915
0x1800348c8  mov     rcx, [rbp+var_10]
0x1800348cc  mov     rax, [rcx]
0x1800348cf  mov     rax, [rax+18h]
0x1800348d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348d8  jmp     short loc_180034913
0x1800348da  mov     rcx, [rbp+var_10]
0x1800348de  mov     rdx, r14
0x1800348e1  mov     rax, [rcx]
0x1800348e4  mov     rax, [rax+30h]
0x1800348e8  jmp     short loc_180034886
0x1800348ea  mov     rcx, [rbp+var_10]
0x1800348ee  mov     rdx, r14
0x1800348f1  mov     rax, [rcx]
0x1800348f4  mov     rax, [rax+38h]
0x1800348f8  jmp     short loc_180034886
0x1800348fa  mov     r8d, 3
0x180034900  mov     rcx, [rbp+var_10]
0x180034904  mov     rdx, rsi
0x180034907  mov     rax, [rcx]
0x18003490a  mov     rax, [rax+40h]
0x18003490e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034913  mov     edi, eax
0x180034915  mov     rcx, [rbp+var_10]
0x180034919  mov     rax, [rcx]
0x18003491c  mov     rax, [rax+10h]
0x180034920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034925  test    edi, edi
0x180034927  jns     short loc_18003495A
0x180034929  mov     rcx, cs:WPP_GLOBAL_Control
0x180034930  lea     rax, WPP_GLOBAL_Control
0x180034937  cmp     rcx, rax
0x18003493a  jz      short loc_18003495A
0x18003493c  test    byte ptr [rcx+1Ch], 1
0x180034940  jz      short loc_18003495A
0x180034942  mov     rcx, [rcx+10h]
0x180034946  lea     r8, WPP_127a71f7b91d3825fada0ff6fce676d2_Traceguids
0x18003494d  mov     edx, 17h
0x180034952  mov     r9d, edi
0x180034955  call    WPP_SF_d
0x18003495a  mov     eax, edi
0x18003495c  mov     rcx, [rbp+var_8]
0x180034960  xor     rcx, rsp; StackCookie
0x180034963  call    __security_check_cookie
0x180034968  mov     rbx, [rsp+40h+arg_0]
0x18003496d  mov     rsi, [rsp+40h+arg_18]
0x180034972  add     rsp, 40h
0x180034976  pop     r14
0x180034978  pop     rdi
0x180034979  pop     rbp
0x18003497a  retn
```
