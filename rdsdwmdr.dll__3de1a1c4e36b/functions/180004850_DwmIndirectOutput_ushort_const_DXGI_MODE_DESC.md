# DwmIndirectOutput(ushort const *,DXGI_MODE_DESC *)

- ea: `0x180004850`
- end: `0x180004986`
- name: `?DwmIndirectOutput@@YAJPEBGPEAUDXGI_MODE_DESC@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct DXGI_MODE_DESC *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004850`
- `0x1800049a4`
- `0x18002b93a`
- `0x18002b960`
- `0x18002c010`

## import_xrefs

- `dxgi!CreateDXGIFactory1` at `0x180004891`
- `dxgi!CreateDXGIFactory1` at `0x180004891`

## pseudocode

```c
__int64 __fastcall DwmIndirectOutput(const unsigned __int16 *a1, struct DXGI_MODE_DESC *a2)
{
  unsigned int v4; // edi
  HRESULT v5; // ebx
  int v6; // eax
  int v7; // eax
  struct IDXGIAdapter1 *v8; // rcx
  HRESULT v9; // eax
  struct IDXGIAdapter1 *v11; // [rsp+20h] [rbp-E0h] BYREF
  void *ppFactory; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v13[320]; // [rsp+30h] [rbp-D0h] BYREF

  v4 = 0;
  ppFactory = 0;
  v5 = CreateDXGIFactory1(&GUID_770aae78_f26f_4dba_a829_253c83d1b387, &ppFactory);
  if ( v5 >= 0 )
  {
    while ( 1 )
    {
      v11 = 0;
      v6 = (*(__int64 (__fastcall **)(void *, _QWORD, struct IDXGIAdapter1 **))(*(_QWORD *)ppFactory + 96LL))(
             ppFactory,
             v4,
             &v11);
      v5 = v6;
      if ( v6 == -2005270526 )
        break;
      if ( v6 < 0 )
        goto LABEL_14;
      memset_0(v13, 0, 0x138u);
      v7 = ((__int64 (__fastcall *)(struct IDXGIAdapter1 *, _BYTE *))v11->lpVtbl->GetDesc1)(v11, v13);
      v8 = v11;
      v5 = v7;
      if ( v7 < 0 )
      {
        if ( !v11 )
          goto LABEL_14;
LABEL_12:
        ((void (__fastcall *)(struct IDXGIAdapter1 *))v8->lpVtbl->Release)(v8);
        goto LABEL_14;
      }
      if ( v11 )
      {
        v9 = EnumerateOutputs(v11, a1, a2);
        v8 = v11;
        v5 = v9;
      }
      if ( !v5 )
        goto LABEL_12;
      if ( v8 )
        ((void (__fastcall *)(struct IDXGIAdapter1 *))v8->lpVtbl->Release)(v8);
      ++v4;
    }
    v5 = 0;
  }
LABEL_14:
  if ( ppFactory )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppFactory + 16LL))(ppFactory);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180004850  mov     [rsp-8+arg_0], rbx
0x180004855  mov     [rsp-8+arg_10], rsi
0x18000485a  push    rbp
0x18000485b  push    rdi
0x18000485c  push    r14
0x18000485e  lea     rbp, [rsp-80h]
0x180004863  sub     rsp, 180h
0x18000486a  mov     rax, cs:__security_cookie
0x180004871  xor     rax, rsp
0x180004874  mov     [rbp+90h+var_20], rax
0x180004878  mov     r14, rdx
0x18000487b  mov     rsi, rcx
0x18000487e  xor     edi, edi
0x180004880  lea     rdx, [rsp+190h+ppFactory]; ppFactory
0x180004885  lea     rcx, _GUID_770aae78_f26f_4dba_a829_253c83d1b387; riid
0x18000488c  mov     [rsp+190h+ppFactory], rdi
0x180004891  call    cs:__imp_CreateDXGIFactory1
0x180004897  mov     ebx, eax
0x180004899  test    eax, eax
0x18000489b  js      loc_18000494A
0x1800048a1  mov     rcx, [rsp+190h+ppFactory]
0x1800048a6  lea     r8, [rsp+190h+var_170]
0x1800048ab  mov     [rsp+190h+var_170], 0
0x1800048b4  mov     edx, edi
0x1800048b6  mov     rax, [rcx]
0x1800048b9  mov     rax, [rax+60h]
0x1800048bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048c2  mov     ebx, eax
0x1800048c4  cmp     eax, 887A0002h
0x1800048c9  jz      short loc_180004948
0x1800048cb  test    eax, eax
0x1800048cd  js      short loc_18000494A
0x1800048cf  xor     edx, edx; Val
0x1800048d1  lea     rcx, [rsp+190h+var_160]; void *
0x1800048d6  mov     r8d, 138h; Size
0x1800048dc  call    memset_0
0x1800048e1  mov     rcx, [rsp+190h+var_170]
0x1800048e6  lea     rdx, [rsp+190h+var_160]
0x1800048eb  mov     rax, [rcx]
0x1800048ee  mov     rax, [rax+50h]
0x1800048f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048f7  mov     rcx, [rsp+190h+var_170]; struct IDXGIAdapter1 *
0x1800048fc  mov     ebx, eax
0x1800048fe  test    eax, eax
0x180004900  js      short loc_180004935
0x180004902  test    rcx, rcx
0x180004905  jz      short loc_180004919
0x180004907  mov     r8, r14; struct DXGI_MODE_DESC *
0x18000490a  mov     rdx, rsi; unsigned __int16 *
0x18000490d  call    ?EnumerateOutputs@@YAJPEAUIDXGIAdapter1@@PEBGPEAUDXGI_MODE_DESC@@@Z; EnumerateOutputs(IDXGIAdapter1 *,ushort const *,DXGI_MODE_DESC *)
0x180004912  mov     rcx, [rsp+190h+var_170]
0x180004917  mov     ebx, eax
0x180004919  test    ebx, ebx
0x18000491b  jz      short loc_18000493A
0x18000491d  test    rcx, rcx
0x180004920  jz      short loc_18000492E
0x180004922  mov     rax, [rcx]
0x180004925  mov     rax, [rax+10h]
0x180004929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000492e  inc     edi
0x180004930  jmp     loc_1800048A1
0x180004935  test    rcx, rcx
0x180004938  jz      short loc_18000494A
0x18000493a  mov     rax, [rcx]
0x18000493d  mov     rax, [rax+10h]
0x180004941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004946  jmp     short loc_18000494A
0x180004948  xor     ebx, ebx
0x18000494a  mov     rcx, [rsp+190h+ppFactory]
0x18000494f  test    rcx, rcx
0x180004952  jz      short loc_180004960
0x180004954  mov     rax, [rcx]
0x180004957  mov     rax, [rax+10h]
0x18000495b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004960  mov     eax, ebx
0x180004962  mov     rcx, [rbp+90h+var_20]
0x180004966  xor     rcx, rsp; StackCookie
0x180004969  call    __security_check_cookie
0x18000496e  lea     r11, [rsp+190h+var_10]
0x180004976  mov     rbx, [r11+20h]
0x18000497a  mov     rsi, [r11+30h]
0x18000497e  mov     rsp, r11
0x180004981  pop     r14
0x180004983  pop     rdi
0x180004984  pop     rbp
0x180004985  retn
```
