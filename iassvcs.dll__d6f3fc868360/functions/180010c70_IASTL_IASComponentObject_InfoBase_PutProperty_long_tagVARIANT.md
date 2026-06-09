# IASTL::IASComponentObject<InfoBase>::PutProperty(long,tagVARIANT *)

- ea: `0x180010c70`
- end: `0x180010cc5`
- name: `?PutProperty@?$IASComponentObject@VInfoBase@@@IASTL@@UEAAJJPEAUtagVARIANT@@@Z`
- size: `85`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010c70`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180010ca0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180010ca0`
- `KERNEL32!EnterCriticalSection` at `0x180010c84`
- `KERNEL32!EnterCriticalSection` at `0x180010c84`
- `KERNEL32!LeaveCriticalSection` at `0x180010cb2`
- `KERNEL32!LeaveCriticalSection` at `0x180010cb2`

## pseudocode

```c
__int64 __fastcall IASTL::IASComponentObject<InfoBase>::PutProperty(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  struct _FILETIME *v3; // rcx
  unsigned int v4; // ebx

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( *(_DWORD *)(a1 + 64) )
  {
    v3 = *(struct _FILETIME **)(a1 + 128);
    if ( v3 )
      GetSystemTimeAsFileTime(v3 + 1);
    v4 = 0;
  }
  else
  {
    v4 = -2147418113;
  }
  LeaveCriticalSection(v1);
  return v4;
}

```

## disassembly

```asm
0x180010c70  mov     [rsp+arg_0], rbx
0x180010c75  push    rdi
0x180010c76  sub     rsp, 20h
0x180010c7a  lea     rdi, [rcx+10h]
0x180010c7e  mov     rbx, rcx
0x180010c81  mov     rcx, rdi; lpCriticalSection
0x180010c84  call    cs:__imp_EnterCriticalSection
0x180010c8a  cmp     dword ptr [rbx+40h], 0
0x180010c8e  jz      short loc_180010CAA
0x180010c90  mov     rcx, [rbx+80h]
0x180010c97  test    rcx, rcx
0x180010c9a  jz      short loc_180010CA6
0x180010c9c  add     rcx, 8; lpSystemTimeAsFileTime
0x180010ca0  call    cs:__imp_GetSystemTimeAsFileTime
0x180010ca6  xor     ebx, ebx
0x180010ca8  jmp     short loc_180010CAF
0x180010caa  mov     ebx, 8000FFFFh
0x180010caf  mov     rcx, rdi; lpCriticalSection
0x180010cb2  call    cs:__imp_LeaveCriticalSection
0x180010cb8  mov     eax, ebx
0x180010cba  mov     rbx, [rsp+28h+arg_0]
0x180010cbf  add     rsp, 20h
0x180010cc3  pop     rdi
0x180010cc4  retn
```
