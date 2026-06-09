# Dfdll::CSystem::GetModuleFileNameW(HINSTANCE__ *,Dfdll::CString &)

- ea: `0x180002ff8`
- end: `0x18000314c`
- name: `?GetModuleFileNameW@CSystem@Dfdll@@SAJPEAUHINSTANCE__@@AEAVCString@2@@Z`
- size: `340`
- prototype: `__int64 __fastcall(HINSTANCE hModule, struct Dfdll::CString *this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180002fbc`
- `0x180006180`
- `0x1800077d0`

## callees

- `0x180001fc8`
- `0x180002238`
- `0x1800026bc`
- `0x180002ff8`
- `0x180012b30`
- `0x18001efd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003120`
- `KERNEL32!GetLastError` at `0x180003120`
- `KERNEL32!GetModuleFileNameW` at `0x180003043`
- `KERNEL32!GetModuleFileNameW` at `0x180003043`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Dfdll::CSystem::GetModuleFileNameW(HINSTANCE hModule, struct Dfdll::CString *this)
{
  unsigned int i; // edi
  DWORD ModuleFileNameW; // eax
  unsigned int v6; // r14d
  const struct std::nothrow_t *v7; // rdx
  int v8; // ebx
  struct std::nothrow_t *v10; // rdi
  const struct std::nothrow_t *v11; // rdx
  signed int LastError; // eax
  const struct std::nothrow_t *v13; // rdx
  void **v14; // [rsp+20h] [rbp-20h] BYREF
  LPWSTR lpFilename; // [rsp+28h] [rbp-18h]
  DWORD nSize; // [rsp+30h] [rbp-10h]

  lpFilename = 0;
  nSize = 0;
  v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
  for ( i = 260; ; i *= 2 )
  {
    v8 = Dfdll::CBufferBase::Allocate((Dfdll::CBufferBase *)&v14, i);
    if ( v8 < 0 )
    {
      v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( lpFilename )
        operator delete(lpFilename, v7);
      return (unsigned int)v8;
    }
    ModuleFileNameW = GetModuleFileNameW(hModule, lpFilename, nSize);
    v6 = ModuleFileNameW;
    if ( !ModuleFileNameW )
    {
      LastError = GetLastError();
      v8 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v8 = LastError;
      v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( lpFilename )
        operator delete(lpFilename, v13);
      return (unsigned int)v8;
    }
    if ( ModuleFileNameW < i )
      break;
  }
  v10 = (struct std::nothrow_t *)lpFilename;
  if ( !lpFilename )
  {
    v8 = Dfdll::CString::AssignNULL(this);
    goto LABEL_14;
  }
  if ( *((_DWORD *)this + 8) )
  {
    v8 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 1) + 40LL))((char *)this + 8, 0);
    if ( v8 < 0 )
    {
LABEL_15:
      v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
      if ( lpFilename )
        operator delete(lpFilename, v11);
      return (unsigned int)v8;
    }
  }
  *((_DWORD *)this + 8) = 0;
  v8 = Dfdll::CString::Append(this, v10, v6);
  if ( v8 < 0 )
  {
LABEL_14:
    if ( v8 < 0 )
      goto LABEL_15;
  }
  v14 = &Dfdll::CBuffer<unsigned short>::`vftable';
  if ( lpFilename )
    operator delete(lpFilename, v11);
  return 0;
}

```

## disassembly

```asm
0x180002ff8  mov     rax, rsp
0x180002ffb  mov     [rax+8], rbx
0x180002fff  mov     [rax+10h], rsi
0x180003003  mov     [rax+18h], rdi
0x180003007  mov     [rax+20h], r13
0x18000300b  push    rbp
0x18000300c  push    r14
0x18000300e  push    r15
0x180003010  mov     rbp, rsp
0x180003013  sub     rsp, 40h
0x180003017  mov     rsi, rdx
0x18000301a  mov     r15, rcx
0x18000301d  and     [rbp+lpFilename], 0
0x180003022  and     [rbp+nSize], 0
0x180003026  lea     r13, ??_7?$CBuffer@G@Dfdll@@6B@; const Dfdll::CBuffer<ushort>::`vftable'
0x18000302d  mov     [rbp+var_20], r13
0x180003031  mov     edi, 104h
0x180003036  jmp     short loc_18000305A
0x180003038  mov     r8d, [rbp+nSize]; nSize
0x18000303c  mov     rdx, [rbp+lpFilename]; lpFilename
0x180003040  mov     rcx, r15; hModule
0x180003043  call    cs:__imp_GetModuleFileNameW
0x180003049  mov     r14d, eax
0x18000304c  test    eax, eax
0x18000304e  jz      loc_180003120
0x180003054  cmp     eax, edi
0x180003056  jb      short loc_18000309E
0x180003058  add     edi, edi
0x18000305a  mov     edx, edi; unsigned int
0x18000305c  lea     rcx, [rbp+var_20]; this
0x180003060  call    ?Allocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Allocate(uint)
0x180003065  test    eax, eax
0x180003067  mov     ebx, eax
0x180003069  jns     short loc_180003038
0x18000306b  mov     [rbp+var_20], r13
0x18000306f  mov     rcx, [rbp+lpFilename]; void *
0x180003073  test    rcx, rcx
0x180003076  jz      short loc_18000307E
0x180003078  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000307d  nop
0x18000307e  mov     eax, ebx
0x180003080  mov     rbx, [rsp+40h+arg_0]
0x180003085  mov     rsi, [rsp+40h+arg_8]
0x18000308a  mov     rdi, [rsp+40h+arg_10]
0x18000308f  mov     r13, [rsp+40h+arg_18]
0x180003094  add     rsp, 40h
0x180003098  pop     r15
0x18000309a  pop     r14
0x18000309c  pop     rbp
0x18000309d  retn
0x18000309e  mov     rdi, [rbp+lpFilename]
0x1800030a2  test    rdi, rdi
0x1800030a5  jnz     short loc_1800030B3
0x1800030a7  mov     rcx, rsi; this
0x1800030aa  call    ?AssignNULL@CString@Dfdll@@IEAAJXZ; Dfdll::CString::AssignNULL(void)
0x1800030af  mov     ebx, eax
0x1800030b1  jmp     short loc_1800030EA
0x1800030b3  cmp     dword ptr [rsi+20h], 0
0x1800030b7  jbe     short loc_1800030D2
0x1800030b9  lea     rcx, [rsi+8]
0x1800030bd  mov     rax, [rcx]
0x1800030c0  xor     edx, edx
0x1800030c2  mov     rax, [rax+28h]
0x1800030c6  call    cs:__guard_dispatch_icall_fptr
0x1800030cc  mov     ebx, eax
0x1800030ce  test    eax, eax
0x1800030d0  js      short loc_1800030EE
0x1800030d2  and     dword ptr [rsi+20h], 0
0x1800030d6  mov     r8d, r14d; unsigned int
0x1800030d9  mov     rdx, rdi; unsigned __int16 *
0x1800030dc  mov     rcx, rsi; this
0x1800030df  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x1800030e4  mov     ebx, eax
0x1800030e6  test    eax, eax
0x1800030e8  jns     short loc_180003106
0x1800030ea  test    ebx, ebx
0x1800030ec  jns     short loc_180003106
0x1800030ee  mov     [rbp+var_20], r13
0x1800030f2  mov     rcx, [rbp+lpFilename]; void *
0x1800030f6  test    rcx, rcx
0x1800030f9  jz      short loc_180003101
0x1800030fb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003100  nop
0x180003101  jmp     loc_18000307E
0x180003106  mov     [rbp+var_20], r13
0x18000310a  mov     rcx, [rbp+lpFilename]; void *
0x18000310e  test    rcx, rcx
0x180003111  jz      short loc_180003119
0x180003113  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003118  nop
0x180003119  xor     ebx, ebx
0x18000311b  jmp     loc_18000307E
0x180003120  call    cs:__imp_GetLastError
0x180003126  movzx   ebx, ax
0x180003129  or      ebx, 80070000h
0x18000312f  test    eax, eax
0x180003131  cmovle  ebx, eax
0x180003134  mov     [rbp+var_20], r13
0x180003138  mov     rcx, [rbp+lpFilename]; void *
0x18000313c  test    rcx, rcx
0x18000313f  jz      short loc_180003147
0x180003141  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003146  nop
0x180003147  jmp     loc_18000307E
```
