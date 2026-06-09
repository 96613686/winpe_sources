# CDropOperation::_DoCopyIteration(void)

- ea: `0x18001465c`
- end: `0x18001479b`
- name: `?_DoCopyIteration@CDropOperation@@IEAAJXZ`
- size: `319`
- prototype: `__int64 __fastcall(CDropOperation *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180014c6c`

## callees

- `0x180002240`
- `0x180002630`
- `0x1800142a0`
- `0x18001465c`
- `0x1800147a4`
- `0x180024134`
- `0x180026f48`
- `0x180028010`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x1800146c7`
- `KERNEL32!lstrlenW` at `0x1800146c7`

## pseudocode

```c
__int64 __fastcall CDropOperation::_DoCopyIteration(CDropOperation *this, __int64 a2, __int64 a3, unsigned int a4)
{
  int v5; // ebx
  unsigned __int64 v6; // rcx
  int v7; // eax
  int v8; // edx
  __int64 v9; // rcx
  unsigned int v11; // [rsp+28h] [rbp-480h]
  unsigned int v12; // [rsp+30h] [rbp-478h]
  unsigned __int16 *v13; // [rsp+40h] [rbp-468h] BYREF
  unsigned __int16 *v14; // [rsp+48h] [rbp-460h] BYREF
  WCHAR String[264]; // [rsp+50h] [rbp-458h] BYREF
  unsigned __int16 v16[264]; // [rsp+260h] [rbp-248h] BYREF

  v14 = (unsigned __int16 *)*((_QWORD *)this + 10);
  v13 = (unsigned __int16 *)*((_QWORD *)this + 11);
  *((_DWORD *)this + 11) = 0;
  do
  {
    v5 = _EnumOneHdrop((const unsigned __int16 **)&v14, (const unsigned __int16 **)&v13, String, a4, v16, v11);
    if ( v5 )
      break;
    v6 = 2LL * lstrlenW(String) + 2;
    if ( v6 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)String + v6) = 0;
    v7 = CDropOperation::_CopyOneHdrop(this, String, v16);
    v9 = *((_QWORD *)this + 9);
    v5 = v7;
    if ( v9 )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v9 + 72LL))(
        v9,
        *((_QWORD *)this + 7),
        *((_QWORD *)this + 8));
    if ( v5 >= 0 )
    {
      if ( v5 == 1 )
        v5 = 0;
    }
    else if ( v5 != -2147023673 )
    {
      DisplayWininetError(*((HWND *)this + 4), v8, v5, a4, 0x195u, v11, v12, *((struct IProgressDialog **)this + 9));
      v5 = -2147023673;
    }
  }
  while ( !v5 );
  Str_SetPtrW((LPWSTR *)this + 10, 0);
  Str_SetPtrW((LPWSTR *)this + 11, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001465c  push    rbx
0x18001465e  push    rsi
0x18001465f  push    rdi
0x180014660  push    r14
0x180014662  sub     rsp, 488h
0x180014669  mov     rax, cs:__security_cookie
0x180014670  xor     rax, rsp
0x180014673  mov     [rsp+4A8h+var_38], rax
0x18001467b  mov     rax, [rcx+50h]
0x18001467f  mov     rdi, rcx
0x180014682  mov     [rsp+4A8h+var_460], rax
0x180014687  mov     rax, [rcx+58h]
0x18001468b  mov     [rsp+4A8h+var_468], rax
0x180014690  mov     dword ptr [rcx+2Ch], 0
0x180014697  lea     rax, [rsp+4A8h+var_248]
0x18001469f  lea     r8, [rsp+4A8h+String]; unsigned __int16 *
0x1800146a4  mov     [rsp+4A8h+var_488], rax; unsigned __int16 *
0x1800146a9  lea     rdx, [rsp+4A8h+var_468]; unsigned __int16 **
0x1800146ae  lea     rcx, [rsp+4A8h+var_460]; unsigned __int16 **
0x1800146b3  call    ?_EnumOneHdrop@@YAJPEAPEBG0PEAGK1K@Z; _EnumOneHdrop(ushort const * *,ushort const * *,ushort *,ulong,ushort *,ulong)
0x1800146b8  mov     ebx, eax
0x1800146ba  test    eax, eax
0x1800146bc  jnz     loc_180014760
0x1800146c2  lea     rcx, [rsp+4A8h+String]; lpString
0x1800146c7  call    cs:__imp_lstrlenW
0x1800146cd  movsxd  rcx, eax
0x1800146d0  lea     rcx, ds:2[rcx*2]
0x1800146d8  cmp     rcx, 208h
0x1800146df  jnb     loc_180014795
0x1800146e5  xor     eax, eax
0x1800146e7  lea     r8, [rsp+4A8h+var_248]; unsigned __int16 *
0x1800146ef  mov     [rsp+rcx+4A8h+String], ax
0x1800146f4  lea     rdx, [rsp+4A8h+String]; unsigned __int16 *
0x1800146f9  mov     rcx, rdi; this
0x1800146fc  call    ?_CopyOneHdrop@CDropOperation@@IEAAJPEBG0@Z; CDropOperation::_CopyOneHdrop(ushort const *,ushort const *)
0x180014701  mov     rcx, [rdi+48h]
0x180014705  mov     ebx, eax
0x180014707  test    rcx, rcx
0x18001470a  jz      short loc_180014720
0x18001470c  mov     rax, [rcx]
0x18001470f  mov     r8, [rdi+40h]
0x180014713  mov     rdx, [rdi+38h]
0x180014717  mov     rax, [rax+48h]
0x18001471b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014720  test    ebx, ebx
0x180014722  jns     short loc_180014750
0x180014724  cmp     ebx, 800704C7h
0x18001472a  jz      short loc_180014758
0x18001472c  mov     rax, [rdi+48h]
0x180014730  mov     r8d, ebx; int
0x180014733  mov     rcx, [rdi+20h]; HWND
0x180014737  mov     [rsp+4A8h+var_470], rax; struct IProgressDialog *
0x18001473c  mov     dword ptr [rsp+4A8h+var_488], 195h; unsigned int
0x180014744  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x180014749  mov     ebx, 800704C7h
0x18001474e  jmp     short loc_180014758
0x180014750  xor     eax, eax
0x180014752  cmp     ebx, 1
0x180014755  cmovz   ebx, eax
0x180014758  test    ebx, ebx
0x18001475a  jz      loc_180014697
0x180014760  xor     edx, edx; psz
0x180014762  lea     rcx, [rdi+50h]; ppsz
0x180014766  call    Str_SetPtrW
0x18001476b  xor     edx, edx; psz
0x18001476d  lea     rcx, [rdi+58h]; ppsz
0x180014771  call    Str_SetPtrW
0x180014776  mov     eax, ebx
0x180014778  mov     rcx, [rsp+4A8h+var_38]
0x180014780  xor     rcx, rsp; StackCookie
0x180014783  call    __security_check_cookie
0x180014788  add     rsp, 488h
0x18001478f  pop     r14
0x180014791  pop     rdi
0x180014792  pop     rsi
0x180014793  pop     rbx
0x180014794  retn
0x180014795  call    __report_rangecheckfailure
```
