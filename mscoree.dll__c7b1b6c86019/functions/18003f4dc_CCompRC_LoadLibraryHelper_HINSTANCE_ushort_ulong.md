# CCompRC::LoadLibraryHelper(HINSTANCE__ * *,ushort *,ulong)

- ea: `0x18003f4dc`
- end: `0x18003f83f`
- name: `?LoadLibraryHelper@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEAGK@Z`
- size: `867`
- prototype: `__int64 __fastcall(CCompRC *__hidden this, HINSTANCE *, wchar_t *Source, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003f38c`

## callees

- `0x18000c1a8`
- `0x180029a5c`
- `0x18002a7a0`
- `0x18003eca4`
- `0x18003eea8`
- `0x18003f4dc`
- `0x18003f848`
- `0x18003fad8`
- `0x18003fd88`
- `0x180041ac0`
- `0x180045020`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18003f52e`
- `KERNEL32!lstrlenW` at `0x18003f5f3`
- `KERNEL32!lstrlenW` at `0x18003f605`
- `KERNEL32!lstrlenW` at `0x18003f52e`
- `KERNEL32!lstrlenW` at `0x18003f5f3`
- `KERNEL32!lstrlenW` at `0x18003f605`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCompRC::LoadLibraryHelper(LPCWSTR *this, HINSTANCE *a2, wchar_t *Source)
{
  wchar_t *v3; // r15
  HINSTANCE *v4; // r12
  LPCWSTR *v5; // rsi
  const unsigned __int16 **v6; // r14
  int v7; // r13d
  __int64 (__fastcall *v8)(unsigned int *); // rax
  int ResourceFile; // ebx
  unsigned int i; // r13d
  unsigned int v11; // edx
  __int64 *v12; // rcx
  wchar_t *v13; // rbx
  wchar_t *v14; // rbx
  const wchar_t *Unicode; // rbx
  unsigned int Count; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  wchar_t *v19; // rcx
  wchar_t *v21; // rbx
  wchar_t *v22; // rcx
  wchar_t *v23; // rcx
  IErrorInfo *v24; // rax
  IErrorInfo *v25; // rbx
  unsigned int v26; // [rsp+50h] [rbp-318h]
  int v27; // [rsp+50h] [rbp-318h]
  unsigned int v28; // [rsp+54h] [rbp-314h]
  int v29; // [rsp+54h] [rbp-314h]
  int v30; // [rsp+58h] [rbp-310h]
  SString *v32; // [rsp+60h] [rbp-308h]
  rsize_t SizeInWordsa; // [rsp+70h] [rbp-2F8h]
  wchar_t *v35; // [rsp+80h] [rbp-2E8h]
  wchar_t *v36; // [rsp+80h] [rbp-2E8h]
  int v38; // [rsp+88h] [rbp-2E0h]
  wchar_t *Destination; // [rsp+90h] [rbp-2D8h] BYREF
  BOOL v40; // [rsp+98h] [rbp-2D0h]
  _QWORD v41[4]; // [rsp+A0h] [rbp-2C8h] BYREF
  unsigned int v42; // [rsp+C0h] [rbp-2A8h] BYREF
  __int64 v43; // [rsp+C8h] [rbp-2A0h] BYREF
  unsigned int v44; // [rsp+D0h] [rbp-298h]
  wchar_t *v45; // [rsp+100h] [rbp-268h] BYREF
  WCHAR String; // [rsp+108h] [rbp-260h] BYREF
  WCHAR Sourcea[264]; // [rsp+110h] [rbp-258h] BYREF

  v3 = Source;
  v4 = a2;
  v5 = this;
  v6 = this + 26;
  v35 = (wchar_t *)(this + 26);
  v7 = lstrlenW(this[26]);
  v30 = v7;
  v42 = 0;
  v43 = 0;
  v44 = 5;
  v8 = (__int64 (__fastcall *)(unsigned int *))v5[28];
  if ( v8 )
  {
    ResourceFile = v8(&v42);
    goto LABEL_12;
  }
  try
  {
    try
    {
      ResourceFile = -2147467259;
      Destination = 0;
      StringArrayList::Append((StringArrayList *)&v42, SString::s_Empty);
    }
    catch ( Exception *v45 )
    {
      Destination = v45;
      throw;
    }
  }
  catch ( ... )
  {
    v29 = IsCurrentExceptionSO();
    v21 = Destination;
    v40 = Destination != 0;
    v41[1] = 0;
    v41[0] = &DelegatingException::`vftable';
    v41[2] = -1;
    v22 = (wchar_t *)v41;
    if ( Destination )
      v22 = Destination;
    v27 = (*(__int64 (__fastcall **)(wchar_t *))(*(_QWORD *)v22 + 16LL))(v22);
    v23 = (wchar_t *)v41;
    if ( v21 )
      v23 = v21;
    v24 = (IErrorInfo *)(*(__int64 (__fastcall **)(wchar_t *))(*(_QWORD *)v23 + 32LL))(v23);
    v25 = v24;
    if ( v24 )
    {
      SetErrorInfo(0, v24);
      ((void (__fastcall *)(IErrorInfo *))v25->lpVtbl->Release)(v25);
    }
    DelegatingException::~DelegatingException((DelegatingException *)v41);
    Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2>::~Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2>(&Destination);
    if ( v29 )
      HandleStackOverflowAfterCatch();
    v6 = (const unsigned __int16 **)v35;
    v3 = Source;
    v4 = a2;
    v5 = this;
    ResourceFile = v27;
LABEL_12:
    if ( ResourceFile == -2147024882 )
    {
      StringArrayList::~StringArrayList((StringArrayList *)&v42);
      return 2147942414LL;
    }
  }
  Sourcea[0] = 0;
  String = 0;
  v3[259] = 0;
  SplitPath(v3, &String, 3, Sourcea, 260, 0, 0, 0, 0);
  v26 = lstrlenW(&String);
  v28 = lstrlenW(Sourcea);
  v38 = v28 + v7 + v26 + 1;
  for ( i = 0; i < v42; ++i )
  {
    v11 = i;
    v12 = &v43;
    if ( i >= v44 )
    {
      do
      {
        v11 -= *((_DWORD *)v12 + 2);
        v12 = (__int64 *)*v12;
      }
      while ( v11 >= *((_DWORD *)v12 + 2) );
    }
    v32 = (SString *)v12[v11 + 2];
    if ( v38 + SString::GetCount(v32) > 0x104 )
    {
      ResourceFile = -2147467259;
    }
    else
    {
      wcscpy_s(v3, v26 + 1, &String);
      v13 = &v3[v26];
      wcscpy_s(v13, v28 + 1, Sourcea);
      v14 = &v13[v28];
      Destination = v14;
      SizeInWordsa = (unsigned int)(v30 + 1);
      if ( *(_DWORD *)v32 >> ((*((_DWORD *)v32 + 2) & 1) == 0) == 1 )
      {
        v36 = (wchar_t *)*v6;
        v19 = &v14[SString::GetCount(v32)];
      }
      else
      {
        Unicode = SString::GetUnicode(v32);
        Count = SString::GetCount(v32);
        wcscpy_s(Destination, Count + 1, Unicode);
        v17 = SString::GetCount(v32);
        wcscpy_s(&Destination[v17], SizeInWordsa, L"\\");
        v36 = (wchar_t *)*v6;
        v18 = SString::GetCount(v32);
        v19 = &Destination[v18 + 1];
      }
      wcscpy_s(v19, SizeInWordsa, v36);
      ResourceFile = CCompRC::LoadResourceFile((CCompRC *)v5, v4, v3);
      if ( ResourceFile >= 0 )
        goto LABEL_21;
    }
  }
  if ( ResourceFile < 0 )
    ResourceFile = CCompRC::LoadResourceFile((CCompRC *)v5, v4, *v6);
LABEL_21:
  StringArrayList::~StringArrayList((StringArrayList *)&v42);
  return (unsigned int)ResourceFile;
}

```

## disassembly

```asm
0x18003f4dc  push    rbx
0x18003f4de  push    rsi
0x18003f4df  push    rdi
0x18003f4e0  push    r12
0x18003f4e2  push    r13
0x18003f4e4  push    r14
0x18003f4e6  push    r15
0x18003f4e8  sub     rsp, 330h
0x18003f4ef  mov     rax, cs:__security_cookie
0x18003f4f6  xor     rax, rsp
0x18003f4f9  mov     [rsp+368h+var_48], rax
0x18003f501  mov     r15, r8
0x18003f504  mov     r12, rdx
0x18003f507  mov     rsi, rcx
0x18003f50a  mov     [rsp+368h+var_308], rcx
0x18003f50f  mov     [rsp+368h+var_2E0], rdx
0x18003f517  mov     [rsp+368h+SizeInWords], r8
0x18003f51c  lea     r14, [rcx+0D0h]
0x18003f523  mov     [rsp+368h+var_2E8], r14
0x18003f52b  mov     rcx, [r14]; lpString
0x18003f52e  call    cs:__imp_lstrlenW
0x18003f534  mov     r13d, eax
0x18003f537  mov     [rsp+368h+var_310], eax
0x18003f53b  xor     edi, edi
0x18003f53d  mov     [rsp+368h+var_2A8], edi
0x18003f544  mov     [rsp+368h+var_2A0], rdi
0x18003f54c  mov     [rsp+368h+var_298], 5
0x18003f557  mov     rax, [rsi+0E0h]
0x18003f55e  test    rax, rax
0x18003f561  jz      short loc_18003F577
0x18003f563  lea     rcx, [rsp+368h+var_2A8]
0x18003f56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f570  mov     ebx, eax
0x18003f572  jmp     loc_18003F788
0x18003f577  mov     ebx, 80004005h
0x18003f57c  mov     [rsp+368h+Destination], rdi
0x18003f584  mov     rdx, cs:?s_Empty@SString@@0PEAV1@EA; struct SString *
0x18003f58b  lea     rcx, [rsp+368h+var_2A8]; this
0x18003f593  call    ?Append@StringArrayList@@QEAAXAEBVSString@@@Z; StringArrayList::Append(SString const &)
0x18003f598  nop
0x18003f599  mov     [rsp+368h+Source], di
0x18003f5a1  mov     [rsp+368h+String], di
0x18003f5a9  mov     [r15+206h], di
0x18003f5b1  mov     [rsp+368h+var_328], rdi; unsigned __int64
0x18003f5b6  mov     [rsp+368h+var_330], rdi; unsigned __int16 *
0x18003f5bb  mov     [rsp+368h+var_338], rdi; SizeInWords
0x18003f5c0  mov     [rsp+368h+var_340], rdi; wchar_t *
0x18003f5c5  mov     [rsp+368h+var_348], 104h; int
0x18003f5cd  lea     r9, [rsp+368h+Source]; unsigned __int16 *
0x18003f5d5  mov     r8d, 3; int
0x18003f5db  lea     rdx, [rsp+368h+String]; Destination
0x18003f5e3  mov     rcx, r15; Source
0x18003f5e6  call    ?SplitPath@@YAXPEBGPEAGH1H1_K12@Z; SplitPath(ushort const *,ushort *,int,ushort *,int,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x18003f5eb  lea     rcx, [rsp+368h+String]; lpString
0x18003f5f3  call    cs:__imp_lstrlenW
0x18003f5f9  mov     [rsp+368h+var_318], eax
0x18003f5fd  lea     rcx, [rsp+368h+Source]; lpString
0x18003f605  call    cs:__imp_lstrlenW
0x18003f60b  mov     [rsp+368h+var_314], eax
0x18003f60f  lea     ecx, [rax+r13]
0x18003f613  mov     eax, [rsp+368h+var_318]
0x18003f617  inc     eax
0x18003f619  add     eax, ecx
0x18003f61b  mov     dword ptr [rsp+368h+var_2E0], eax
0x18003f622  mov     r13d, edi
0x18003f625  cmp     [rsp+368h+var_2A8], edi
0x18003f62c  jbe     loc_18003F7F9
0x18003f632  mov     edx, r13d
0x18003f635  lea     rcx, [rsp+368h+var_2A0]
0x18003f63d  cmp     r13d, [rsp+368h+var_298]
0x18003f645  jb      short loc_18003F652
0x18003f647  sub     edx, [rcx+8]
0x18003f64a  mov     rcx, [rcx]
0x18003f64d  cmp     edx, [rcx+8]
0x18003f650  jnb     short loc_18003F647
0x18003f652  mov     eax, edx
0x18003f654  mov     rax, [rcx+rax*8+10h]
0x18003f659  mov     [rsp+368h+var_308], rax
0x18003f65e  mov     rcx, rax; this
0x18003f661  call    ?GetCount@SString@@QEBAIXZ; SString::GetCount(void)
0x18003f666  add     eax, dword ptr [rsp+368h+var_2E0]
0x18003f66d  cmp     eax, 104h
0x18003f672  ja      loc_18003F7E3
0x18003f678  mov     ebx, [rsp+368h+var_318]
0x18003f67c  lea     edx, [rbx+1]; SizeInWords
0x18003f67f  lea     r8, [rsp+368h+String]; Source
0x18003f687  mov     rcx, r15; Destination
0x18003f68a  call    wcscpy_s
0x18003f68f  lea     rbx, [r15+rbx*2]
0x18003f693  mov     edx, [rsp+368h+var_314]
0x18003f697  inc     edx; SizeInWords
0x18003f699  lea     r8, [rsp+368h+Source]; Source
0x18003f6a1  mov     rcx, rbx; Destination
0x18003f6a4  call    wcscpy_s
0x18003f6a9  mov     eax, [rsp+368h+var_314]
0x18003f6ad  lea     rbx, [rbx+rax*2]
0x18003f6b1  mov     [rsp+368h+Destination], rbx
0x18003f6b9  mov     eax, [rsp+368h+var_310]
0x18003f6bd  inc     eax
0x18003f6bf  mov     [rsp+368h+SizeInWords], rax
0x18003f6c4  mov     rdx, [rsp+368h+var_308]
0x18003f6c9  mov     ecx, [rdx+8]
0x18003f6cc  not     ecx
0x18003f6ce  and     ecx, 1
0x18003f6d1  mov     eax, [rdx]
0x18003f6d3  shr     eax, cl
0x18003f6d5  mov     rcx, rdx; this
0x18003f6d8  cmp     eax, 1
0x18003f6db  jz      loc_18003F7A5
0x18003f6e1  call    ?GetUnicode@SString@@QEBAPEBGXZ; SString::GetUnicode(void)
0x18003f6e6  mov     rbx, rax
0x18003f6e9  mov     rcx, [rsp+368h+var_308]; this
0x18003f6ee  call    ?GetCount@SString@@QEBAIXZ; SString::GetCount(void)
0x18003f6f3  lea     edx, [rax+1]; SizeInWords
0x18003f6f6  mov     r8, rbx; Source
0x18003f6f9  mov     rcx, [rsp+368h+Destination]; Destination
0x18003f701  call    wcscpy_s
0x18003f706  mov     rcx, [rsp+368h+var_308]; this
0x18003f70b  call    ?GetCount@SString@@QEBAIXZ; SString::GetCount(void)
0x18003f710  mov     eax, eax
0x18003f712  mov     rcx, [rsp+368h+Destination]
0x18003f71a  lea     rcx, [rcx+rax*2]; Destination
0x18003f71e  lea     r8, asc_18004C8C0; "\\"
0x18003f725  mov     rdx, [rsp+368h+SizeInWords]; SizeInWords
0x18003f72a  call    wcscpy_s
0x18003f72f  mov     rax, [r14]
0x18003f732  mov     [rsp+368h+var_2E8], rax
0x18003f73a  mov     rcx, [rsp+368h+var_308]; this
0x18003f73f  call    ?GetCount@SString@@QEBAIXZ; SString::GetCount(void)
0x18003f744  mov     eax, eax
0x18003f746  mov     rcx, [rsp+368h+Destination]
0x18003f74e  lea     rcx, [rcx+rax*2]
0x18003f752  add     rcx, 2
0x18003f756  jmp     short loc_18003F7BB
0x18003f758  xor     edi, edi
0x18003f75a  cmp     [rsp+368h+var_314], edi
0x18003f75e  jz      short loc_18003F765
0x18003f760  call    ?HandleStackOverflowAfterCatch@@YAXXZ; HandleStackOverflowAfterCatch(void)
0x18003f765  mov     r13d, [rsp+368h+var_310]
0x18003f76a  mov     r14, [rsp+368h+var_2E8]
0x18003f772  mov     r15, [rsp+368h+SizeInWords]
0x18003f777  mov     r12, [rsp+368h+var_2E0]
0x18003f77f  mov     rsi, [rsp+368h+var_308]
0x18003f784  mov     ebx, [rsp+368h+var_318]
0x18003f788  cmp     ebx, 8007000Eh
0x18003f78e  jnz     loc_18003F599
0x18003f794  lea     rcx, [rsp+368h+var_2A8]; this
0x18003f79c  call    ??1StringArrayList@@QEAA@XZ; StringArrayList::~StringArrayList(void)
0x18003f7a1  mov     eax, ebx
0x18003f7a3  jmp     short loc_18003F81C
0x18003f7a5  mov     rax, [r14]
0x18003f7a8  mov     [rsp+368h+var_2E8], rax
0x18003f7b0  call    ?GetCount@SString@@QEBAIXZ; SString::GetCount(void)
0x18003f7b5  mov     eax, eax
0x18003f7b7  lea     rcx, [rbx+rax*2]; Destination
0x18003f7bb  mov     r8, [rsp+368h+var_2E8]; Source
0x18003f7c3  mov     rdx, [rsp+368h+SizeInWords]; SizeInWords
0x18003f7c8  call    wcscpy_s
0x18003f7cd  mov     r8, r15; unsigned __int16 *
0x18003f7d0  mov     rdx, r12; HINSTANCE *
0x18003f7d3  mov     rcx, rsi; this
0x18003f7d6  call    ?LoadResourceFile@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEBG@Z; CCompRC::LoadResourceFile(HINSTANCE__ * *,ushort const *)
0x18003f7db  mov     ebx, eax
0x18003f7dd  test    eax, eax
0x18003f7df  jns     short loc_18003F80D
0x18003f7e1  jmp     short loc_18003F7E8
0x18003f7e3  mov     ebx, 80004005h
0x18003f7e8  inc     r13d
0x18003f7eb  cmp     r13d, [rsp+368h+var_2A8]
0x18003f7f3  jb      loc_18003F632
0x18003f7f9  test    ebx, ebx
0x18003f7fb  jns     short loc_18003F80D
0x18003f7fd  mov     r8, [r14]; unsigned __int16 *
0x18003f800  mov     rdx, r12; HINSTANCE *
0x18003f803  mov     rcx, rsi; this
0x18003f806  call    ?LoadResourceFile@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@PEBG@Z; CCompRC::LoadResourceFile(HINSTANCE__ * *,ushort const *)
0x18003f80b  mov     ebx, eax
0x18003f80d  lea     rcx, [rsp+368h+var_2A8]; this
0x18003f815  call    ??1StringArrayList@@QEAA@XZ; StringArrayList::~StringArrayList(void)
0x18003f81a  mov     eax, ebx
0x18003f81c  mov     rcx, [rsp+368h+var_48]
0x18003f824  xor     rcx, rsp; StackCookie
0x18003f827  call    __security_check_cookie
0x18003f82c  add     rsp, 330h
0x18003f833  pop     r15
0x18003f835  pop     r14
0x18003f837  pop     r13
0x18003f839  pop     r12
0x18003f83b  pop     rdi
0x18003f83c  pop     rsi
0x18003f83d  pop     rbx
0x18003f83e  retn
```
