# OleGetObjectDescriptorDataFromOleObject(IOleObject *,ulong,_POINTL,tagSIZE *)

- ea: `0x18008c2dc`
- end: `0x18008c565`
- name: `?OleGetObjectDescriptorDataFromOleObject@@YAPEAXPEAUIOleObject@@KU_POINTL@@PEAUtagSIZE@@@Z`
- size: `649`
- prototype: `void *__fastcall(struct IOleObject *, unsigned int, struct _POINTL, struct tagSIZE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task`

## callers

- `0x18005a618`

## callees

- `0x180041adc`
- `0x18004a778`
- `0x18008c2dc`
- `0x18008d624`
- `0x1800907ac`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18008c3b5`
- `msvcrt!wcscpy_s` at `0x18008c3dc`
- `msvcrt!wcscpy_s` at `0x18008c3b5`
- `msvcrt!wcscpy_s` at `0x18008c3dc`

## string_xrefs

- `0x18008c3a5`: `Linked `
- `0x18008c45e`: `CreateBindCtx`

## pseudocode

```c
void *__fastcall OleGetObjectDescriptorDataFromOleObject(
        struct IOleObject *a1,
        unsigned int a2,
        struct _POINTL a3,
        struct tagSIZE *a4)
{
  struct IOleObjectVtbl *lpVtbl; // rax
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
  void *v19; // rbx
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
      SetProcAddr((char *)Ole32Procs + 16, 1, "CreateBindCtx");
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
  v19 = AllocObjectDescriptor((__int128 *)v27, a2, *(__int64 *)v23, *(_QWORD *)&a3, v22, Destination, v24);
  CW32System::CoTaskMemFree(v24);
  return v19;
}

```

## disassembly

```asm
0x18008c2dc  push    rbp
0x18008c2de  push    rbx
0x18008c2df  push    rsi
0x18008c2e0  push    rdi
0x18008c2e1  push    r14
0x18008c2e3  push    r15
0x18008c2e5  lea     rbp, [rsp-3A8h]
0x18008c2ed  sub     rsp, 4A8h
0x18008c2f4  mov     rax, cs:__security_cookie
0x18008c2fb  xor     rax, rsp
0x18008c2fe  mov     [rbp+3D0h+var_40], rax
0x18008c305  mov     rax, [rcx]
0x18008c308  mov     rbx, r8
0x18008c30b  mov     r15d, edx
0x18008c30e  mov     [rsp+4D0h+Source], 0
0x18008c317  xorps   xmm0, xmm0
0x18008c31a  mov     [rsp+4D0h+var_478], 0
0x18008c323  lea     r8, [rsp+4D0h+var_470]
0x18008c328  mov     [rsp+4D0h+var_470], 0
0x18008c331  mov     rax, [rax]
0x18008c334  lea     rdx, IID_IOleLink
0x18008c33b  mov     r14, r9
0x18008c33e  mov     [rsp+4D0h+var_488], 0
0x18008c346  mov     rdi, rcx
0x18008c349  mov     qword ptr [rsp+4D0h+var_480], 0
0x18008c352  movups  [rbp+3D0h+var_450], xmm0
0x18008c356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c35b  mov     rcx, [rdi]
0x18008c35e  lea     rdx, [rbp+3D0h+var_450]
0x18008c362  mov     esi, eax
0x18008c364  mov     rax, [rcx+78h]
0x18008c368  mov     rcx, rdi
0x18008c36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c370  test    eax, eax
0x18008c372  jns     short loc_18008C37B
0x18008c374  xorps   xmm0, xmm0
0x18008c377  movups  [rbp+3D0h+var_450], xmm0
0x18008c37b  mov     rax, [rdi]
0x18008c37e  lea     r8, [rsp+4D0h+Source]
0x18008c383  mov     edx, 1
0x18008c388  mov     rcx, rdi
0x18008c38b  mov     rax, [rax+80h]
0x18008c392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c397  mov     rcx, [rsp+4D0h+Source]; void *
0x18008c39c  test    esi, esi
0x18008c39e  js      short loc_18008C3CB
0x18008c3a0  test    rcx, rcx
0x18008c3a3  jz      short loc_18008C3E9
0x18008c3a5  lea     r8, aLinked; "Linked "
0x18008c3ac  mov     edx, 200h; SizeInWords
0x18008c3b1  lea     rcx, [rbp+3D0h+Destination]; Destination
0x18008c3b5  call    cs:__imp_wcscpy_s
0x18008c3bb  mov     r8, [rsp+4D0h+Source]
0x18008c3c0  lea     rcx, [rbp+3D0h+var_432]
0x18008c3c4  mov     edx, 1F9h
0x18008c3c9  jmp     short loc_18008C3DC
0x18008c3cb  test    rcx, rcx
0x18008c3ce  jz      short loc_18008C3E9
0x18008c3d0  mov     r8, rcx; Source
0x18008c3d3  mov     edx, 200h; SizeInWords
0x18008c3d8  lea     rcx, [rbp+3D0h+Destination]; Destination
0x18008c3dc  call    cs:__imp_wcscpy_s
0x18008c3e2  mov     rcx, [rsp+4D0h+Source]
0x18008c3e7  jmp     short loc_18008C3EF
0x18008c3e9  xor     eax, eax
0x18008c3eb  mov     [rbp+3D0h+Destination], ax
0x18008c3ef  call    ?CoTaskMemFree@CW32System@@SAXPEAX@Z; CW32System::CoTaskMemFree(void *)
0x18008c3f4  test    esi, esi
0x18008c3f6  js      short loc_18008C418
0x18008c3f8  mov     rcx, [rsp+4D0h+var_470]
0x18008c3fd  lea     rdx, [rsp+4D0h+var_478]
0x18008c402  mov     rax, [rcx]
0x18008c405  mov     rax, [rax+40h]
0x18008c409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c40e  mov     rcx, [rsp+4D0h+var_470]
0x18008c413  jmp     loc_18008C4C2
0x18008c418  mov     rax, [rdi]
0x18008c41b  lea     r9, [rsp+4D0h+var_460]
0x18008c420  mov     edx, 4
0x18008c425  mov     qword ptr [rsp+4D0h+var_460], 0
0x18008c42e  mov     rcx, rdi
0x18008c431  mov     rax, [rax+40h]
0x18008c435  lea     r8d, [rdx-1]
0x18008c439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c43e  test    eax, eax
0x18008c440  js      loc_18008C4CE
0x18008c446  mov     [rsp+4D0h+var_468], 0
0x18008c44f  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18008c454  lea     rsi, [rax+10h]
0x18008c458  cmp     qword ptr [rsi], 0
0x18008c45c  jnz     short loc_18008C472
0x18008c45e  lea     r8, aCreatebindctx; "CreateBindCtx"
0x18008c465  mov     edx, 1
0x18008c46a  mov     rcx, rsi
0x18008c46d  call    SetProcAddr
0x18008c472  mov     rax, [rsi]
0x18008c475  test    rax, rax
0x18008c478  jz      short loc_18008C486
0x18008c47a  lea     rdx, [rsp+4D0h+var_468]
0x18008c47f  xor     ecx, ecx
0x18008c481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c486  mov     rcx, qword ptr [rsp+4D0h+var_460]
0x18008c48b  test    rcx, rcx
0x18008c48e  jz      short loc_18008C4CE
0x18008c490  mov     rax, [rcx]
0x18008c493  lea     r9, [rsp+4D0h+var_478]
0x18008c498  mov     rdx, [rsp+4D0h+var_468]
0x18008c49d  xor     r8d, r8d
0x18008c4a0  mov     rax, [rax+0A0h]
0x18008c4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c4ac  mov     rcx, [rsp+4D0h+var_468]
0x18008c4b1  mov     rax, [rcx]
0x18008c4b4  mov     rax, [rax+10h]
0x18008c4b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c4bd  mov     rcx, qword ptr [rsp+4D0h+var_460]
0x18008c4c2  mov     rax, [rcx]
0x18008c4c5  mov     rax, [rax+10h]
0x18008c4c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c4ce  mov     rax, [rdi]
0x18008c4d1  lea     r8, [rsp+4D0h+var_488]
0x18008c4d6  mov     edx, r15d
0x18008c4d9  mov     rcx, rdi
0x18008c4dc  mov     rax, [rax+0B0h]
0x18008c4e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c4e8  test    r14, r14
0x18008c4eb  jz      short loc_18008C4FC
0x18008c4ed  mov     eax, [r14]
0x18008c4f0  mov     [rsp+4D0h+var_480], eax
0x18008c4f4  mov     eax, [r14+4]
0x18008c4f8  mov     [rsp+4D0h+var_480+4], eax
0x18008c4fc  mov     rax, [rsp+4D0h+var_478]
0x18008c501  lea     rcx, [rsp+4D0h+var_460]; int
0x18008c506  movaps  xmm0, [rbp+3D0h+var_450]
0x18008c50a  mov     r9, rbx; int
0x18008c50d  mov     r8, qword ptr [rsp+4D0h+var_480]; int
0x18008c512  mov     edx, r15d; int
0x18008c515  mov     [rsp+4D0h+var_4A0], rax; unsigned __int16 *
0x18008c51a  lea     rax, [rbp+3D0h+Destination]
0x18008c51e  mov     [rsp+4D0h+Src], rax; Src
0x18008c523  mov     eax, [rsp+4D0h+var_488]
0x18008c527  mov     [rsp+4D0h+var_4B0], eax; int
0x18008c52b  movdqa  xmmword ptr [rsp+4D0h+var_460], xmm0
0x18008c531  call    AllocObjectDescriptor
0x18008c536  mov     rcx, [rsp+4D0h+var_478]; void *
0x18008c53b  mov     rbx, rax
0x18008c53e  call    ?CoTaskMemFree@CW32System@@SAXPEAX@Z; CW32System::CoTaskMemFree(void *)
0x18008c543  mov     rax, rbx
0x18008c546  mov     rcx, [rbp+3D0h+var_40]
0x18008c54d  xor     rcx, rsp; StackCookie
0x18008c550  call    __security_check_cookie
0x18008c555  add     rsp, 4A8h
0x18008c55c  pop     r15
0x18008c55e  pop     r14
0x18008c560  pop     rdi
0x18008c561  pop     rsi
0x18008c562  pop     rbx
0x18008c563  pop     rbp
0x18008c564  retn
```
