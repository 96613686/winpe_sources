# CWMWriterProperties::GetProfileIndexFromGuid(ulong *,_GUID)

- ea: `0x180012514`
- end: `0x1800126d8`
- name: `?GetProfileIndexFromGuid@CWMWriterProperties@@AEAAJPEAKU_GUID@@@Z`
- size: `452`
- prototype: `int(CWMWriterProperties *__hidden this, unsigned int *, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180012850`

## callees

- `0x180001460`
- `0x180012514`
- `0x18001e5b9`
- `0x18001f010`

## import_xrefs

- `WMVCore!WMCreateProfileManager` at `0x180012560`
- `WMVCore!WMCreateProfileManager` at `0x180012560`

## pseudocode

```c
__int64 __fastcall CWMWriterProperties::GetProfileIndexFromGuid(
        CWMWriterProperties *this,
        unsigned int *a2,
        struct _GUID *a3)
{
  HRESULT v6; // ebx
  int v7; // r14d
  unsigned int v8; // edi
  __int64 v9; // [rsp+20h] [rbp-48h] BYREF
  signed int v10; // [rsp+28h] [rbp-40h] BYREF
  IWMProfileManager *ppProfileManager; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+38h] [rbp-30h] BYREF
  __int128 Buf1; // [rsp+40h] [rbp-28h] BYREF

  if ( !a2 )
    return 2147500035LL;
  ppProfileManager = 0;
  v10 = 0;
  *a2 = 0;
  v6 = WMCreateProfileManager(&ppProfileManager);
  if ( v6 >= 0 )
  {
    v9 = 0;
    if ( ((__int64 (__fastcall *)(IWMProfileManager *, GUID *, __int64 *))ppProfileManager->lpVtbl->QueryInterface)(
           ppProfileManager,
           &IID_IWMProfileManager2,
           &v9) >= 0 )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 80LL))(v9, 0x80000);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    v6 = ((__int64 (__fastcall *)(IWMProfileManager *, signed int *))ppProfileManager->lpVtbl->GetSystemProfileCount)(
           ppProfileManager,
           &v10);
    if ( v6 >= 0 )
    {
      v7 = 0;
      v8 = 0;
      do
      {
        if ( (int)v8 >= v10 )
          break;
        v12 = 0;
        v6 = ((__int64 (__fastcall *)(IWMProfileManager *, _QWORD, __int64 *))ppProfileManager->lpVtbl->LoadSystemProfile)(
               ppProfileManager,
               v8,
               &v12);
        if ( v6 >= 0 )
        {
          v9 = 0;
          v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v12)(v12, &IID_IWMProfile2, &v9);
          if ( v6 >= 0 )
          {
            Buf1 = 0;
            v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v9 + 168LL))(v9, &Buf1);
            if ( v6 >= 0 && !memcmp_0(&Buf1, a3, 0x10u) )
            {
              *a2 = v8;
              v7 = 1;
            }
          }
          if ( v9 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        ++v8;
      }
      while ( !v7 );
    }
  }
  if ( ppProfileManager )
    ((void (__fastcall *)(IWMProfileManager *))ppProfileManager->lpVtbl->Release)(ppProfileManager);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012514  push    rbp
0x180012516  push    rbx
0x180012517  push    rsi
0x180012518  push    rdi
0x180012519  push    r14
0x18001251b  push    r15
0x18001251d  mov     rbp, rsp
0x180012520  sub     rsp, 68h
0x180012524  mov     rax, cs:__security_cookie
0x18001252b  xor     rax, rsp
0x18001252e  mov     [rbp+var_18], rax
0x180012532  mov     r15, r8
0x180012535  mov     rsi, rdx
0x180012538  test    rdx, rdx
0x18001253b  jnz     short loc_180012547
0x18001253d  mov     eax, 80004003h
0x180012542  jmp     loc_1800126BF
0x180012547  lea     rcx, [rbp+ppProfileManager]; ppProfileManager
0x18001254b  mov     [rbp+ppProfileManager], 0
0x180012553  mov     [rbp+var_40], 0
0x18001255a  mov     dword ptr [rdx], 0
0x180012560  call    cs:__imp_WMCreateProfileManager
0x180012566  mov     ebx, eax
0x180012568  test    eax, eax
0x18001256a  js      loc_1800126A8
0x180012570  mov     rcx, [rbp+ppProfileManager]
0x180012574  lea     r8, [rbp+var_48]
0x180012578  mov     [rbp+var_48], 0
0x180012580  lea     rdx, IID_IWMProfileManager2
0x180012587  mov     rax, [rcx]
0x18001258a  mov     rax, [rax]
0x18001258d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012592  test    eax, eax
0x180012594  js      short loc_1800125BB
0x180012596  mov     rcx, [rbp+var_48]
0x18001259a  mov     edx, 80000h
0x18001259f  mov     rax, [rcx]
0x1800125a2  mov     rax, [rax+50h]
0x1800125a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125ab  mov     rcx, [rbp+var_48]
0x1800125af  mov     rax, [rcx]
0x1800125b2  mov     rax, [rax+10h]
0x1800125b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125bb  mov     rcx, [rbp+ppProfileManager]
0x1800125bf  lea     rdx, [rbp+var_40]
0x1800125c3  mov     rax, [rcx]
0x1800125c6  mov     rax, [rax+38h]
0x1800125ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125cf  mov     ebx, eax
0x1800125d1  test    eax, eax
0x1800125d3  js      loc_1800126A8
0x1800125d9  xor     r14d, r14d
0x1800125dc  xor     edi, edi
0x1800125de  cmp     edi, [rbp+var_40]
0x1800125e1  jge     loc_1800126A8
0x1800125e7  mov     rcx, [rbp+ppProfileManager]
0x1800125eb  lea     r8, [rbp+var_30]
0x1800125ef  mov     [rbp+var_30], 0
0x1800125f7  mov     edx, edi
0x1800125f9  mov     rax, [rcx]
0x1800125fc  mov     rax, [rax+40h]
0x180012600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012605  mov     ebx, eax
0x180012607  test    eax, eax
0x180012609  js      short loc_180012688
0x18001260b  mov     rcx, [rbp+var_30]
0x18001260f  lea     r8, [rbp+var_48]
0x180012613  mov     [rbp+var_48], 0
0x18001261b  lea     rdx, IID_IWMProfile2
0x180012622  mov     rax, [rcx]
0x180012625  mov     rax, [rax]
0x180012628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001262d  mov     ebx, eax
0x18001262f  test    eax, eax
0x180012631  js      short loc_180012673
0x180012633  mov     rcx, [rbp+var_48]
0x180012637  lea     rdx, [rbp+Buf1]
0x18001263b  xorps   xmm0, xmm0
0x18001263e  movups  [rbp+Buf1], xmm0
0x180012642  mov     rax, [rcx]
0x180012645  mov     rax, [rax+0A8h]
0x18001264c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012651  mov     ebx, eax
0x180012653  test    eax, eax
0x180012655  js      short loc_180012673
0x180012657  mov     r8d, 10h; Size
0x18001265d  lea     rcx, [rbp+Buf1]; Buf1
0x180012661  mov     rdx, r15; Buf2
0x180012664  call    memcmp_0
0x180012669  test    eax, eax
0x18001266b  jnz     short loc_180012673
0x18001266d  mov     [rsi], edi
0x18001266f  lea     r14d, [rax+1]
0x180012673  mov     rcx, [rbp+var_48]
0x180012677  test    rcx, rcx
0x18001267a  jz      short loc_180012688
0x18001267c  mov     rax, [rcx]
0x18001267f  mov     rax, [rax+10h]
0x180012683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012688  mov     rcx, [rbp+var_30]
0x18001268c  test    rcx, rcx
0x18001268f  jz      short loc_18001269D
0x180012691  mov     rax, [rcx]
0x180012694  mov     rax, [rax+10h]
0x180012698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001269d  inc     edi
0x18001269f  test    r14d, r14d
0x1800126a2  jz      loc_1800125DE
0x1800126a8  mov     rcx, [rbp+ppProfileManager]
0x1800126ac  test    rcx, rcx
0x1800126af  jz      short loc_1800126BD
0x1800126b1  mov     rax, [rcx]
0x1800126b4  mov     rax, [rax+10h]
0x1800126b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126bd  mov     eax, ebx
0x1800126bf  mov     rcx, [rbp+var_18]
0x1800126c3  xor     rcx, rsp; StackCookie
0x1800126c6  call    __security_check_cookie
0x1800126cb  add     rsp, 68h
0x1800126cf  pop     r15
0x1800126d1  pop     r14
0x1800126d3  pop     rdi
0x1800126d4  pop     rsi
0x1800126d5  pop     rbx
0x1800126d6  pop     rbp
0x1800126d7  retn
```
