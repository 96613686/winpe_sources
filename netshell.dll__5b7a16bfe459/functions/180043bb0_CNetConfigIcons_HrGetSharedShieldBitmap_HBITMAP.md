# CNetConfigIcons::HrGetSharedShieldBitmap(HBITMAP__ * *)

- ea: `0x180043bb0`
- end: `0x180043cba`
- name: `?HrGetSharedShieldBitmap@CNetConfigIcons@@QEAAJPEAPEAUHBITMAP__@@@Z`
- size: `266`
- prototype: `__int64 __fastcall(CNetConfigIcons *__hidden this, HBITMAP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004d034`

## callees

- `0x180043bb0`
- `0x180049a08`
- `0x180060b8c`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x180043beb`
- `USER32!GetSystemMetrics` at `0x180043bfd`
- `USER32!GetSystemMetrics` at `0x180043beb`
- `USER32!GetSystemMetrics` at `0x180043bfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043c9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043c9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043bdf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043bdf`
- `GDI32!DeleteObject` at `0x180043c23`
- `GDI32!DeleteObject` at `0x180043c23`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNetConfigIcons::HrGetSharedShieldBitmap(CNetConfigIcons *this, HBITMAP *a2)
{
  CNetConfigIcons *v3; // rbp
  struct _RTL_CRITICAL_SECTION *v4; // r12
  LONG SystemMetrics; // r14d
  LONG v6; // eax
  int v7; // r15d
  HBITMAP *v8; // rsi
  void *v9; // rcx
  int v10; // ebx
  __int64 v11; // rdx
  void **v12; // r8
  tagSIZE v14; // [rsp+70h] [rbp+8h] BYREF
  HICON hicon; // [rsp+80h] [rbp+18h] BYREF
  char *v16; // [rsp+88h] [rbp+20h]

  v14 = (tagSIZE)this;
  v3 = g_pNetConfigIcons;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)g_pNetConfigIcons + 8);
  v16 = (char *)g_pNetConfigIcons + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pNetConfigIcons + 8));
  SystemMetrics = GetSystemMetrics(49);
  v14.cx = SystemMetrics;
  v6 = GetSystemMetrics(50);
  v7 = v6;
  v14.cy = v6;
  v8 = (HBITMAP *)((char *)v3 + 104);
  v9 = (void *)*((_QWORD *)v3 + 13);
  if ( v9 )
  {
    if ( *((_DWORD *)v3 + 28) == SystemMetrics )
    {
      v10 = 0;
      if ( *((_DWORD *)v3 + 29) == v6 )
        goto LABEL_8;
    }
    DeleteObject(v9);
    *v8 = 0;
  }
  hicon = 0;
  v10 = LoadIconWithScaleDown(0, (PCWSTR)0x4E, SystemMetrics, v7, &hicon);
  if ( v10 >= 0 )
  {
    v10 = CreateBitmapFromIcon(hicon, v11, v12, &v14, (HBITMAP *)v3 + 13);
    if ( v10 >= 0 )
    {
      *((tagSIZE *)v3 + 14) = v14;
LABEL_8:
      if ( *v8 )
        *a2 = *v8;
      else
        v10 = -2147418113;
    }
  }
  LeaveCriticalSection(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180043bb0  mov     rax, rsp
0x180043bb3  mov     [rax+10h], rbx
0x180043bb7  mov     [rax+8], rcx
0x180043bbb  push    rbp
0x180043bbc  push    rsi
0x180043bbd  push    rdi
0x180043bbe  push    r12
0x180043bc0  push    r13
0x180043bc2  push    r14
0x180043bc4  push    r15
0x180043bc6  sub     rsp, 30h
0x180043bca  mov     r13, rdx
0x180043bcd  mov     rbp, cs:?g_pNetConfigIcons@@3PEAVCNetConfigIcons@@EA; CNetConfigIcons * g_pNetConfigIcons
0x180043bd4  lea     r12, [rbp+8]
0x180043bd8  mov     [rax+20h], r12
0x180043bdc  mov     rcx, r12; lpCriticalSection
0x180043bdf  call    cs:__imp_EnterCriticalSection
0x180043be5  nop
0x180043be6  mov     ecx, 31h ; '1'; nIndex
0x180043beb  call    cs:__imp_GetSystemMetrics
0x180043bf1  mov     r14d, eax
0x180043bf4  mov     [rsp+68h+arg_0.cx], eax
0x180043bf8  mov     ecx, 32h ; '2'; nIndex
0x180043bfd  call    cs:__imp_GetSystemMetrics
0x180043c03  mov     r15d, eax
0x180043c06  mov     [rsp+68h+arg_0.cy], eax
0x180043c0a  lea     rsi, [rbp+68h]
0x180043c0e  mov     rcx, [rsi]; ho
0x180043c11  test    rcx, rcx
0x180043c14  jz      short loc_180043C30
0x180043c16  cmp     [rbp+70h], r14d
0x180043c1a  jnz     short loc_180043C23
0x180043c1c  xor     ebx, ebx
0x180043c1e  cmp     [rbp+74h], eax
0x180043c21  jz      short loc_180043C87
0x180043c23  call    cs:__imp_DeleteObject
0x180043c29  mov     qword ptr [rsi], 0
0x180043c30  mov     [rsp+68h+hicon], 0
0x180043c3c  lea     rax, [rsp+68h+hicon]
0x180043c44  mov     [rsp+68h+phico], rax; phico
0x180043c49  mov     r9d, r15d; cy
0x180043c4c  mov     r8d, r14d; cx
0x180043c4f  mov     edx, 4Eh ; 'N'; pszName
0x180043c54  xor     ecx, ecx; hinst
0x180043c56  call    LoadIconWithScaleDown
0x180043c5b  mov     ebx, eax
0x180043c5d  test    eax, eax
0x180043c5f  js      short loc_180043C9A
0x180043c61  mov     [rsp+68h+phico], rsi; HBITMAP *
0x180043c66  lea     r9, [rsp+68h+arg_0]; struct tagSIZE *
0x180043c6b  mov     rcx, [rsp+68h+hicon]; hicon
0x180043c73  call    ?CreateBitmapFromIcon@@YAJPEAUHICON__@@HHPEBUtagSIZE@@PEAPEAUHBITMAP__@@@Z; CreateBitmapFromIcon(HICON__ *,int,int,tagSIZE const *,HBITMAP__ * *)
0x180043c78  mov     ebx, eax
0x180043c7a  test    eax, eax
0x180043c7c  js      short loc_180043C9A
0x180043c7e  mov     rax, qword ptr [rsp+68h+arg_0.cx]
0x180043c83  mov     [rbp+70h], rax
0x180043c87  mov     rax, [rsi]
0x180043c8a  test    rax, rax
0x180043c8d  jz      short loc_180043C95
0x180043c8f  mov     [r13+0], rax
0x180043c93  jmp     short loc_180043C9A
0x180043c95  mov     ebx, 8000FFFFh
0x180043c9a  mov     rcx, r12; lpCriticalSection
0x180043c9d  call    cs:__imp_LeaveCriticalSection
0x180043ca3  mov     eax, ebx
0x180043ca5  mov     rbx, [rsp+68h+arg_8]
0x180043caa  add     rsp, 30h
0x180043cae  pop     r15
0x180043cb0  pop     r14
0x180043cb2  pop     r13
0x180043cb4  pop     r12
0x180043cb6  pop     rdi
0x180043cb7  pop     rsi
0x180043cb8  pop     rbp
0x180043cb9  retn
```
