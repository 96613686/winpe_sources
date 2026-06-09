# IASTL::IASComponentObject<NTEventLog>::PutProperty(long,tagVARIANT *)

- ea: `0x180010cd0`
- end: `0x180010d1e`
- name: `?PutProperty@?$IASComponentObject@VNTEventLog@@@IASTL@@UEAAJJPEAUtagVARIANT@@@Z`
- size: `78`
- prototype: `__int64 __fastcall(NTEventLog *this, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180010cd0`
- `0x180015200`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180010ce8`
- `KERNEL32!EnterCriticalSection` at `0x180010ce8`
- `KERNEL32!LeaveCriticalSection` at `0x180010d0d`
- `KERNEL32!LeaveCriticalSection` at `0x180010d0d`

## pseudocode

```c
__int64 __fastcall IASTL::IASComponentObject<NTEventLog>::PutProperty(NTEventLog *this, int a2, struct tagVARIANT *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  unsigned int v7; // ebx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_DWORD *)this + 16) )
    v7 = NTEventLog::PutProperty(this, a2, a3);
  else
    v7 = -2147418113;
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x180010cd0  push    rbx
0x180010cd2  push    rbp
0x180010cd3  push    rsi
0x180010cd4  push    rdi
0x180010cd5  sub     rsp, 28h
0x180010cd9  lea     rdi, [rcx+10h]
0x180010cdd  mov     rbx, rcx
0x180010ce0  mov     rcx, rdi; lpCriticalSection
0x180010ce3  mov     rsi, r8
0x180010ce6  mov     ebp, edx
0x180010ce8  call    cs:__imp_EnterCriticalSection
0x180010cee  cmp     dword ptr [rbx+40h], 0
0x180010cf2  jz      short loc_180010D05
0x180010cf4  mov     r8, rsi; struct tagVARIANT *
0x180010cf7  mov     edx, ebp; int
0x180010cf9  mov     rcx, rbx; this
0x180010cfc  call    ?PutProperty@NTEventLog@@UEAAJJPEAUtagVARIANT@@@Z; NTEventLog::PutProperty(long,tagVARIANT *)
0x180010d01  mov     ebx, eax
0x180010d03  jmp     short loc_180010D0A
0x180010d05  mov     ebx, 8000FFFFh
0x180010d0a  mov     rcx, rdi; lpCriticalSection
0x180010d0d  call    cs:__imp_LeaveCriticalSection
0x180010d13  mov     eax, ebx
0x180010d15  add     rsp, 28h
0x180010d19  pop     rdi
0x180010d1a  pop     rsi
0x180010d1b  pop     rbp
0x180010d1c  pop     rbx
0x180010d1d  retn
```
