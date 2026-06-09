# OleGetObjectDescriptorDataFromOleObject(IOleObject *,ulong,_POINTL,tagSIZE *)

- ea: `0x18008e9e0`
- end: `0x18008ec76`
- name: `?OleGetObjectDescriptorDataFromOleObject@@YAPEAXPEAUIOleObject@@KU_POINTL@@PEAUtagSIZE@@@Z`
- size: `662`
- prototype: `void *(struct IOleObject *, unsigned int, struct _POINTL, struct tagSIZE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x18005bc58`

## callees

- `0x1800427ac`
- `0x18004b92c`
- `0x18008e9e0`
- `0x18008fe00`
- `0x1800931b0`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18008eab9`
- `msvcrt!wcscpy_s` at `0x18008eae6`
- `msvcrt!wcscpy_s` at `0x18008eab9`
- `msvcrt!wcscpy_s` at `0x18008eae6`

## string_xrefs

- `0x18008eaa9`: `Linked `
- `0x18008eb6e`: `CreateBindCtx`

## pseudocode

```c
__int64 __fastcall OleGetObjectDescriptorDataFromOleObject(
        struct IOleObject *a1,
        unsigned int a2,
        struct _POINTL a3,
        struct tagSIZE *a4)
{
  struct IOleObjectVtbl *lpVtbl; // rax
  LONG x; // ebx
  HRESULT (__stdcall *QueryInterface)(IOleObject *, const IID *const, void **); // rax
  int v10; // esi
  wchar_t *v11; // rcx
  wchar_t *v12; // r8
  wchar_t *v13; // rcx
  rsize_t v14; // rdx
  __int64 v15; // rcx
  struct IOleObjectVtbl *v16; // rax
  struct COLE32_PROC *Ole32Procs; // rax
  struct COLE32_PROC *v18; // rsi
  __int64 v19; // rbx
  wchar_t *Source; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  int v23[2]; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v24; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  int v27[4]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v28; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Destination[7]; // [rsp+90h] [rbp-70h] BYREF
  char v30; // [rsp+9Eh] [rbp-62h] BYREF

  lpVtbl = a1->lpVtbl;
  x = a3.x;
  Source = 0;
  v24 = 0;
  v25 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  v22 = 0;
  *(_QWORD *)v23 = 0;
  v28 = 0;
  v10 = ((__int64 (__fastcall *)(struct IOleObject *, GUID *, __int64 *))QueryInterface)(a1, &IID_IOleLink, &v25);
  if ( ((int (__fastcall *)(struct IOleObject *, __int128 *))a1->lpVtbl->GetUserClassID)(a1, &v28) < 0 )
    v28 = 0;
  ((void (__fastcall *)(struct IOleObject *, __int64, wchar_t **))a1->lpVtbl->GetUserType)(a1, 1, &Source);
  v11 = Source;
  if ( v10 < 0 )
  {
    if ( Source )
    {
      v12 = Source;
      v14 = 512;
      v13 = Destination;
      goto LABEL_8;
    }
  }
  else if ( Source )
  {
    wcscpy_s(Destination, 0x200u, L"Linked ");
    v12 = Source;
    v13 = (wchar_t *)&v30;
    v14 = 505;
LABEL_8:
    wcscpy_s(v13, v14, v12);
    v11 = Source;
    goto LABEL_10;
  }
  Destination[0] = 0;
LABEL_10:
  CW32System::CoTaskMemFree(v11);
  if ( v10 >= 0 )
  {
    (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v25 + 64LL))(v25, &v24);
    v15 = v25;
LABEL_19:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_20;
  }
  v16 = a1->lpVtbl;
  *(_QWORD *)v27 = 0;
  if ( ((int (__fastcall *)(struct IOleObject *, __int64, __int64, int *))v16->GetMoniker)(a1, 4, 3, v27) >= 0 )
  {
    v26 = 0;
    Ole32Procs = CThreadData::GetOle32Procs();
    v18 = (struct COLE32_PROC *)((char *)Ole32Procs + 16);
    if ( !*((_QWORD *)Ole32Procs + 2) )
      SetProcAddr((FARPROC *)Ole32Procs + 2, 1, "CreateBindCtx");
    if ( *(_QWORD *)v18 )
      (*(void (__fastcall **)(_QWORD, __int64 *))v18)(0, &v26);
    if ( *(_QWORD *)v27 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD, unsigned __int16 **))(**(_QWORD **)v27 + 160LL))(
        *(_QWORD *)v27,
        v26,
        0,
        &v24);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      v15 = *(_QWORD *)v27;
      goto LABEL_19;
    }
  }
LABEL_20:
  ((void (__fastcall *)(struct IOleObject *, _QWORD, int *))a1->lpVtbl->GetMiscStatus)(a1, a2, &v22);
  if ( a4 )
  {
    v23[0] = a4->cx;
    v23[1] = a4->cy;
  }
  *(_OWORD *)v27 = v28;
  v19 = AllocObjectDescriptor((int)v27, a2, v23[0], x, v22, Destination, v24);
  CW32System::CoTaskMemFree(v24);
  return v19;
}

```

## disassembly

```asm
0x18008e9e0  push    rbp
0x18008e9e2  push    rbx
0x18008e9e3  push    rsi
0x18008e9e4  push    rdi
0x18008e9e5  push    r14
0x18008e9e7  push    r15
0x18008e9e9  lea     rbp, [rsp-3A8h]
0x18008e9f1  sub     rsp, 4A8h
0x18008e9f8  mov     rax, cs:__security_cookie
0x18008e9ff  xor     rax, rsp
0x18008ea02  mov     [rbp+3D0h+var_40], rax
0x18008ea09  mov     rax, [rcx]
0x18008ea0c  mov     rbx, r8
0x18008ea0f  mov     r15d, edx
0x18008ea12  mov     [rsp+4D0h+Source], 0
0x18008ea1b  xorps   xmm0, xmm0
0x18008ea1e  mov     [rsp+4D0h+var_478], 0
0x18008ea27  lea     r8, [rsp+4D0h+var_470]
0x18008ea2c  mov     [rsp+4D0h+var_470], 0
0x18008ea35  mov     rax, [rax]
0x18008ea38  lea     rdx, IID_IOleLink
0x18008ea3f  mov     r14, r9
0x18008ea42  mov     [rsp+4D0h+var_488], 0
0x18008ea4a  mov     rdi, rcx
0x18008ea4d  mov     qword ptr [rsp+4D0h+var_480], 0
0x18008ea56  movups  [rbp+3D0h+var_450], xmm0
0x18008ea5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea5f  mov     rcx, [rdi]
0x18008ea62  lea     rdx, [rbp+3D0h+var_450]
0x18008ea66  mov     esi, eax
0x18008ea68  mov     rax, [rcx+78h]
0x18008ea6c  mov     rcx, rdi
0x18008ea6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea74  test    eax, eax
0x18008ea76  jns     short loc_18008EA7F
0x18008ea78  xorps   xmm0, xmm0
0x18008ea7b  movups  [rbp+3D0h+var_450], xmm0
0x18008ea7f  mov     rax, [rdi]
0x18008ea82  lea     r8, [rsp+4D0h+Source]
0x18008ea87  mov     edx, 1
0x18008ea8c  mov     rcx, rdi
0x18008ea8f  mov     rax, [rax+80h]
0x18008ea96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea9b  mov     rcx, [rsp+4D0h+Source]; void *
0x18008eaa0  test    esi, esi
0x18008eaa2  js      short loc_18008EAD5
0x18008eaa4  test    rcx, rcx
0x18008eaa7  jz      short loc_18008EAF9
0x18008eaa9  lea     r8, aLinked; "Linked "
0x18008eab0  mov     edx, 200h; SizeInWords
0x18008eab5  lea     rcx, [rbp+3D0h+Destination]; Destination
0x18008eab9  call    cs:__imp_wcscpy_s
0x18008eac0  nop     dword ptr [rax+rax+00h]
0x18008eac5  mov     r8, [rsp+4D0h+Source]
0x18008eaca  lea     rcx, [rbp+3D0h+var_432]
0x18008eace  mov     edx, 1F9h
0x18008ead3  jmp     short loc_18008EAE6
0x18008ead5  test    rcx, rcx
0x18008ead8  jz      short loc_18008EAF9
0x18008eada  mov     r8, rcx; Source
0x18008eadd  mov     edx, 200h; SizeInWords
0x18008eae2  lea     rcx, [rbp+3D0h+Destination]; Destination
0x18008eae6  call    cs:__imp_wcscpy_s
0x18008eaed  nop     dword ptr [rax+rax+00h]
0x18008eaf2  mov     rcx, [rsp+4D0h+Source]
0x18008eaf7  jmp     short loc_18008EAFF
0x18008eaf9  xor     eax, eax
0x18008eafb  mov     [rbp+3D0h+Destination], ax
0x18008eaff  call    ?CoTaskMemFree@CW32System@@SAXPEAX@Z; CW32System::CoTaskMemFree(void *)
0x18008eb04  test    esi, esi
0x18008eb06  js      short loc_18008EB28
0x18008eb08  mov     rcx, [rsp+4D0h+var_470]
0x18008eb0d  lea     rdx, [rsp+4D0h+var_478]
0x18008eb12  mov     rax, [rcx]
0x18008eb15  mov     rax, [rax+40h]
0x18008eb19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eb1e  mov     rcx, [rsp+4D0h+var_470]
0x18008eb23  jmp     loc_18008EBD2
0x18008eb28  mov     rax, [rdi]
0x18008eb2b  lea     r9, [rsp+4D0h+var_460]
0x18008eb30  mov     edx, 4
0x18008eb35  mov     qword ptr [rsp+4D0h+var_460], 0
0x18008eb3e  mov     rcx, rdi
0x18008eb41  mov     rax, [rax+40h]
0x18008eb45  lea     r8d, [rdx-1]
0x18008eb49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eb4e  test    eax, eax
0x18008eb50  js      loc_18008EBDE
0x18008eb56  mov     [rsp+4D0h+var_468], 0
0x18008eb5f  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18008eb64  lea     rsi, [rax+10h]
0x18008eb68  cmp     qword ptr [rsi], 0
0x18008eb6c  jnz     short loc_18008EB82
0x18008eb6e  lea     r8, aCreatebindctx; "CreateBindCtx"
0x18008eb75  mov     edx, 1
0x18008eb7a  mov     rcx, rsi
0x18008eb7d  call    SetProcAddr
0x18008eb82  mov     rax, [rsi]
0x18008eb85  test    rax, rax
0x18008eb88  jz      short loc_18008EB96
0x18008eb8a  lea     rdx, [rsp+4D0h+var_468]
0x18008eb8f  xor     ecx, ecx
0x18008eb91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eb96  mov     rcx, qword ptr [rsp+4D0h+var_460]
0x18008eb9b  test    rcx, rcx
0x18008eb9e  jz      short loc_18008EBDE
0x18008eba0  mov     rax, [rcx]
0x18008eba3  lea     r9, [rsp+4D0h+var_478]
0x18008eba8  mov     rdx, [rsp+4D0h+var_468]
0x18008ebad  xor     r8d, r8d
0x18008ebb0  mov     rax, [rax+0A0h]
0x18008ebb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ebbc  mov     rcx, [rsp+4D0h+var_468]
0x18008ebc1  mov     rax, [rcx]
0x18008ebc4  mov     rax, [rax+10h]
0x18008ebc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ebcd  mov     rcx, qword ptr [rsp+4D0h+var_460]
0x18008ebd2  mov     rax, [rcx]
0x18008ebd5  mov     rax, [rax+10h]
0x18008ebd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ebde  mov     rax, [rdi]
0x18008ebe1  lea     r8, [rsp+4D0h+var_488]
0x18008ebe6  mov     edx, r15d
0x18008ebe9  mov     rcx, rdi
0x18008ebec  mov     rax, [rax+0B0h]
0x18008ebf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ebf8  test    r14, r14
0x18008ebfb  jz      short loc_18008EC0C
0x18008ebfd  mov     eax, [r14]
0x18008ec00  mov     [rsp+4D0h+var_480], eax
0x18008ec04  mov     eax, [r14+4]
0x18008ec08  mov     [rsp+4D0h+var_480+4], eax
0x18008ec0c  mov     rax, [rsp+4D0h+var_478]
0x18008ec11  lea     rcx, [rsp+4D0h+var_460]; int
0x18008ec16  movaps  xmm0, [rbp+3D0h+var_450]
0x18008ec1a  mov     r9, rbx; int
0x18008ec1d  mov     r8, qword ptr [rsp+4D0h+var_480]; int
0x18008ec22  mov     edx, r15d; int
0x18008ec25  mov     [rsp+4D0h+var_4A0], rax; unsigned __int16 *
0x18008ec2a  lea     rax, [rbp+3D0h+Destination]
0x18008ec2e  mov     [rsp+4D0h+Src], rax; Src
0x18008ec33  mov     eax, [rsp+4D0h+var_488]
0x18008ec37  mov     [rsp+4D0h+var_4B0], eax; int
0x18008ec3b  movdqa  xmmword ptr [rsp+4D0h+var_460], xmm0
0x18008ec41  call    AllocObjectDescriptor
0x18008ec46  mov     rcx, [rsp+4D0h+var_478]; void *
0x18008ec4b  mov     rbx, rax
0x18008ec4e  call    ?CoTaskMemFree@CW32System@@SAXPEAX@Z; CW32System::CoTaskMemFree(void *)
0x18008ec53  mov     rax, rbx
0x18008ec56  mov     rcx, [rbp+3D0h+var_40]
0x18008ec5d  xor     rcx, rsp; StackCookie
0x18008ec60  call    __security_check_cookie
0x18008ec65  add     rsp, 4A8h
0x18008ec6c  pop     r15
0x18008ec6e  pop     r14
0x18008ec70  pop     rdi
0x18008ec71  pop     rsi
0x18008ec72  pop     rbx
0x18008ec73  pop     rbp
0x18008ec74  retn
```
