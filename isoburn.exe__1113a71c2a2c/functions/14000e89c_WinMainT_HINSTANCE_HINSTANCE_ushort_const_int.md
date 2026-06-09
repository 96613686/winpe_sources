# WinMainT(HINSTANCE__ *,HINSTANCE__ *,ushort const *,int)

- ea: `0x14000e89c`
- end: `0x14000eb5c`
- name: `?WinMainT@@YAHPEAUHINSTANCE__@@0PEBGH@Z`
- size: `704`
- prototype: `int(HINSTANCE, HINSTANCE, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000ed60`

## callees

- `0x140001fa0`
- `0x14000469c`
- `0x14000a904`
- `0x14000cef4`
- `0x14000e130`
- `0x14000e89c`
- `0x14000ecf8`
- `0x14000ed30`
- `0x140010010`

## import_xrefs

- `USER32!LoadStringW` at `0x14000ea67`
- `USER32!LoadStringW` at `0x14000ea86`
- `USER32!LoadStringW` at `0x14000ea67`
- `USER32!LoadStringW` at `0x14000ea86`
- `USER32!MessageBoxW` at `0x14000eaa0`
- `USER32!MessageBoxW` at `0x14000eaa0`
- `api-ms-win-crt-private-l1-1-0!_o_isalpha` at `0x14000e9ce`
- `api-ms-win-crt-private-l1-1-0!_o_isalpha` at `0x14000e9ce`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x14000e9e2`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x14000e9e2`
- `SHLWAPI!__imp_StrCmpICW` at `0x14000e99c`
- `SHLWAPI!__imp_StrCmpICW` at `0x14000e99c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000e8e0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000e8e0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000eb29`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000eb29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000ea2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000eaa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000ea2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000eaa9`

## pseudocode

```c
__int64 __fastcall WinMainT(HINSTANCE a1, HINSTANCE a2, const unsigned __int16 *a3)
{
  unsigned __int16 *v4; // r14
  __int64 v5; // rcx
  __int64 *v6; // rbx
  __int64 v7; // rsi
  __int64 *v8; // rbx
  __int64 *v9; // rax
  int v10; // r15d
  unsigned __int16 v11; // r12
  void *v12; // r13
  const WCHAR *Token; // rax
  unsigned __int16 *v14; // rdi
  int v15; // ebx
  _QWORD *v16; // rbx
  __int64 v17; // rcx
  void (__fastcall *v18)(_QWORD); // rax
  __int64 *v19; // rbx
  __int64 *v20; // rax
  LPVOID pv; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v23; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Text[520]; // [rsp+240h] [rbp+140h] BYREF

  v4 = 0;
  v23 = 0;
  McGenEventRegister_EventRegister(a1, a2);
  if ( CoInitializeEx(0, 0) < 0 )
    goto LABEL_39;
  v6 = &qword_140016730;
  v7 = -1;
  if ( &qword_140016730 != (__int64 *)-1LL )
  {
    qword_140016848 = (__int64)&qword_140016730;
    if ( qword_140016730 )
    {
      do
      {
        LOBYTE(v5) = 1;
        ((void (__fastcall *)(__int64))v6[8])(v5);
        v6 += 9;
      }
      while ( *v6 );
    }
  }
  v8 = off_1400162D0[0];
  v9 = off_1400162D8;
  while ( v8 < v9 )
  {
    if ( *v8 )
    {
      LOBYTE(v5) = 1;
      (*(void (__fastcall **)(__int64))(*v8 + 64))(v5);
      v9 = off_1400162D8;
    }
    ++v8;
  }
  pv = 0;
  if ( (int)CoAllocString(a3, (unsigned __int16 **)&pv) < 0 )
    goto LABEL_26;
  v10 = 0;
  v11 = 0;
  v12 = pv;
  Token = NextToken((unsigned __int16 **)&pv);
  v14 = (unsigned __int16 *)Token;
  if ( !Token )
    goto LABEL_22;
  if ( !StrCmpICW(Token, L"/Q") )
  {
    v10 = 1;
    v14 = NextToken((unsigned __int16 **)&pv);
    if ( !v14 )
      goto LABEL_22;
  }
  do
    ++v7;
  while ( v14[v7] );
  if ( v7 == 2 )
  {
    if ( (unsigned int)_o_isalpha(*v14) )
    {
      if ( v14[1] == 58 )
      {
        v11 = toupper(*v14);
        v14 = NextToken((unsigned __int16 **)&pv);
        if ( !v14 )
          goto LABEL_22;
      }
    }
  }
  v15 = CoAllocString(v14, &v23);
  if ( v15 >= 0 && NextToken((unsigned __int16 **)&pv) )
  {
    v4 = v23;
LABEL_22:
    v15 = -2147024809;
    goto LABEL_23;
  }
  v4 = v23;
LABEL_23:
  CoTaskMemFree(v12);
  if ( v15 < 0 )
  {
LABEL_26:
    LoadStringW(hInstance, 0xFFu, Buffer, 260);
    LoadStringW(hInstance, 0x100u, Text, 520);
    MessageBoxW(0, Text, Buffer, 0x40u);
    goto LABEL_27;
  }
  DoISOImageBurn(v4, v11, v10);
LABEL_27:
  CoTaskMemFree(v4);
  v16 = (_QWORD *)qword_140016848;
  if ( qword_140016848 )
  {
    while ( *v16 )
    {
      v17 = v16[4];
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v18 = (void (__fastcall *)(_QWORD))v16[8];
      v16[4] = 0;
      v18(0);
      v16 += 9;
    }
  }
  v19 = off_1400162D0[0];
  v20 = off_1400162D8;
  while ( v19 < v20 )
  {
    if ( *v19 )
    {
      (*(void (__fastcall **)(_QWORD))(*v19 + 64))(0);
      v20 = off_1400162D8;
    }
    ++v19;
  }
  ATL::CAtlModule::Term((ATL::CAtlModule *)&_Module);
  CoUninitialize();
LABEL_39:
  McGenEventUnregister_EventUnregister();
  return 1;
}

```

## disassembly

```asm
0x14000e89c  push    rbp
0x14000e89e  push    rbx
0x14000e89f  push    rsi
0x14000e8a0  push    rdi
0x14000e8a1  push    r12
0x14000e8a3  push    r13
0x14000e8a5  push    r14
0x14000e8a7  push    r15
0x14000e8a9  lea     rbp, [rsp-568h]
0x14000e8b1  sub     rsp, 668h
0x14000e8b8  mov     rax, cs:__security_cookie
0x14000e8bf  xor     rax, rsp
0x14000e8c2  mov     [rbp+5A0h+var_50], rax
0x14000e8c9  xor     r13d, r13d
0x14000e8cc  mov     rdi, r8
0x14000e8cf  mov     r14d, r13d
0x14000e8d2  mov     [rsp+6A0h+var_678], r13
0x14000e8d7  call    McGenEventRegister_EventRegister
0x14000e8dc  xor     edx, edx; dwCoInit
0x14000e8de  xor     ecx, ecx; pvReserved
0x14000e8e0  call    cs:__imp_CoInitializeEx
0x14000e8e6  test    eax, eax
0x14000e8e8  js      loc_14000EB2F
0x14000e8ee  lea     rbx, qword_140016730
0x14000e8f5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000e8f9  cmp     rbx, rsi
0x14000e8fc  jz      short loc_14000E922
0x14000e8fe  cmp     cs:qword_140016730, r13
0x14000e905  mov     cs:qword_140016848, rbx
0x14000e90c  jz      short loc_14000E922
0x14000e90e  mov     rax, [rbx+40h]
0x14000e912  mov     cl, 1
0x14000e914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e919  lea     rbx, [rbx+48h]
0x14000e91d  cmp     [rbx], r13
0x14000e920  jnz     short loc_14000E90E
0x14000e922  mov     rbx, cs:off_1400162D0
0x14000e929  mov     rax, cs:off_1400162D8
0x14000e930  jmp     short loc_14000E950
0x14000e932  mov     rdx, [rbx]
0x14000e935  test    rdx, rdx
0x14000e938  jz      short loc_14000E94C
0x14000e93a  mov     rax, [rdx+40h]
0x14000e93e  mov     cl, 1
0x14000e940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e945  mov     rax, cs:off_1400162D8
0x14000e94c  add     rbx, 8
0x14000e950  cmp     rbx, rax
0x14000e953  jb      short loc_14000E932
0x14000e955  lea     rdx, [rsp+6A0h+pv]; unsigned __int16 **
0x14000e95a  mov     [rsp+6A0h+pv], r13
0x14000e95f  mov     rcx, rdi; unsigned __int16 *
0x14000e962  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x14000e967  test    eax, eax
0x14000e969  js      loc_14000EA51
0x14000e96f  mov     r15d, r13d
0x14000e972  lea     rcx, [rsp+6A0h+pv]; unsigned __int16 **
0x14000e977  mov     r12d, r13d
0x14000e97a  mov     r13, [rsp+6A0h+pv]
0x14000e97f  call    ?NextToken@@YAPEAGPEAPEAG@Z; NextToken(ushort * *)
0x14000e984  xor     ebx, ebx
0x14000e986  mov     rdi, rax
0x14000e989  test    rax, rax
0x14000e98c  jz      loc_14000EA24
0x14000e992  lea     rdx, pszStr2; "/Q"
0x14000e999  mov     rcx, rax; pszStr1
0x14000e99c  call    cs:__imp_StrCmpICW
0x14000e9a2  test    eax, eax
0x14000e9a4  jnz     short loc_14000E9BC
0x14000e9a6  lea     rcx, [rsp+6A0h+pv]; unsigned __int16 **
0x14000e9ab  call    ?NextToken@@YAPEAGPEAPEAG@Z; NextToken(ushort * *)
0x14000e9b0  lea     r15d, [rbx+1]
0x14000e9b4  mov     rdi, rax
0x14000e9b7  test    rax, rax
0x14000e9ba  jz      short loc_14000EA24
0x14000e9bc  inc     rsi
0x14000e9bf  cmp     [rdi+rsi*2], bx
0x14000e9c3  jnz     short loc_14000E9BC
0x14000e9c5  cmp     rsi, 2
0x14000e9c9  jnz     short loc_14000E9FD
0x14000e9cb  movzx   ecx, word ptr [rdi]
0x14000e9ce  call    cs:__imp__o_isalpha
0x14000e9d4  test    eax, eax
0x14000e9d6  jz      short loc_14000E9FD
0x14000e9d8  cmp     word ptr [rdi+2], 3Ah ; ':'
0x14000e9dd  jnz     short loc_14000E9FD
0x14000e9df  movzx   ecx, word ptr [rdi]; C
0x14000e9e2  call    cs:__imp_toupper
0x14000e9e8  lea     rcx, [rsp+6A0h+pv]; unsigned __int16 **
0x14000e9ed  mov     r12d, eax
0x14000e9f0  call    ?NextToken@@YAPEAGPEAPEAG@Z; NextToken(ushort * *)
0x14000e9f5  mov     rdi, rax
0x14000e9f8  test    rax, rax
0x14000e9fb  jz      short loc_14000EA24
0x14000e9fd  lea     rdx, [rsp+6A0h+var_678]; unsigned __int16 **
0x14000ea02  mov     rcx, rdi; unsigned __int16 *
0x14000ea05  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x14000ea0a  mov     ebx, eax
0x14000ea0c  test    eax, eax
0x14000ea0e  js      short loc_14000EA4A
0x14000ea10  lea     rcx, [rsp+6A0h+pv]; unsigned __int16 **
0x14000ea15  call    ?NextToken@@YAPEAGPEAPEAG@Z; NextToken(ushort * *)
0x14000ea1a  test    rax, rax
0x14000ea1d  jz      short loc_14000EA4A
0x14000ea1f  mov     r14, [rsp+6A0h+var_678]
0x14000ea24  mov     ebx, 80070057h
0x14000ea29  mov     rcx, r13; pv
0x14000ea2c  call    cs:__imp_CoTaskMemFree
0x14000ea32  xor     r13d, r13d
0x14000ea35  test    ebx, ebx
0x14000ea37  js      short loc_14000EA51
0x14000ea39  mov     r8d, r15d; int
0x14000ea3c  movzx   edx, r12w; unsigned __int16
0x14000ea40  mov     rcx, r14; unsigned __int16 *
0x14000ea43  call    ?DoISOImageBurn@@YAJPEBGGH@Z; DoISOImageBurn(ushort const *,ushort,int)
0x14000ea48  jmp     short loc_14000EAA6
0x14000ea4a  mov     r14, [rsp+6A0h+var_678]
0x14000ea4f  jmp     short loc_14000EA29
0x14000ea51  mov     rcx, cs:hInstance; hInstance
0x14000ea58  lea     r8, [rsp+6A0h+Buffer]; lpBuffer
0x14000ea5d  mov     r9d, 104h; cchBufferMax
0x14000ea63  lea     edx, [r9-5]; uID
0x14000ea67  call    cs:__imp_LoadStringW
0x14000ea6d  mov     rcx, cs:hInstance; hInstance
0x14000ea74  lea     r8, [rbp+5A0h+Text]; lpBuffer
0x14000ea7b  mov     r9d, 208h; cchBufferMax
0x14000ea81  mov     edx, 100h; uID
0x14000ea86  call    cs:__imp_LoadStringW
0x14000ea8c  mov     r9d, 40h ; '@'; uType
0x14000ea92  lea     r8, [rsp+6A0h+Buffer]; lpCaption
0x14000ea97  lea     rdx, [rbp+5A0h+Text]; lpText
0x14000ea9e  xor     ecx, ecx; hWnd
0x14000eaa0  call    cs:__imp_MessageBoxW
0x14000eaa6  mov     rcx, r14; pv
0x14000eaa9  call    cs:__imp_CoTaskMemFree
0x14000eaaf  mov     rbx, cs:qword_140016848
0x14000eab6  test    rbx, rbx
0x14000eab9  jz      short loc_14000EAEA
0x14000eabb  jmp     short loc_14000EAE5
0x14000eabd  mov     rcx, [rbx+20h]
0x14000eac1  test    rcx, rcx
0x14000eac4  jz      short loc_14000EAD2
0x14000eac6  mov     rax, [rcx]
0x14000eac9  mov     rax, [rax+10h]
0x14000eacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ead2  mov     rax, [rbx+40h]
0x14000ead6  xor     ecx, ecx
0x14000ead8  mov     [rbx+20h], r13
0x14000eadc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eae1  add     rbx, 48h ; 'H'
0x14000eae5  cmp     [rbx], r13
0x14000eae8  jnz     short loc_14000EABD
0x14000eaea  mov     rbx, cs:off_1400162D0
0x14000eaf1  mov     rax, cs:off_1400162D8
0x14000eaf8  jmp     short loc_14000EB18
0x14000eafa  mov     rdx, [rbx]
0x14000eafd  test    rdx, rdx
0x14000eb00  jz      short loc_14000EB14
0x14000eb02  mov     rax, [rdx+40h]
0x14000eb06  xor     ecx, ecx
0x14000eb08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb0d  mov     rax, cs:off_1400162D8
0x14000eb14  add     rbx, 8
0x14000eb18  cmp     rbx, rax
0x14000eb1b  jb      short loc_14000EAFA
0x14000eb1d  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x14000eb24  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x14000eb29  call    cs:__imp_CoUninitialize
0x14000eb2f  call    McGenEventUnregister_EventUnregister
0x14000eb34  mov     eax, 1
0x14000eb39  mov     rcx, [rbp+5A0h+var_50]
0x14000eb40  xor     rcx, rsp; StackCookie
0x14000eb43  call    __security_check_cookie
0x14000eb48  add     rsp, 668h
0x14000eb4f  pop     r15
0x14000eb51  pop     r14
0x14000eb53  pop     r13
0x14000eb55  pop     r12
0x14000eb57  pop     rdi
0x14000eb58  pop     rsi
0x14000eb59  pop     rbx
0x14000eb5a  pop     rbp
0x14000eb5b  retn
```
