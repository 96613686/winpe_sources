# IASTL::IASComponentObject<NTEventLog>::GetProperty(long,tagVARIANT *)

- ea: `0x18000fff0`
- end: `0x180010017`
- name: `?GetProperty@?$IASComponentObject@VNTEventLog@@@IASTL@@UEAAJJPEAUtagVARIANT@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000fffd`
- `KERNEL32!EnterCriticalSection` at `0x18000fffd`
- `KERNEL32!LeaveCriticalSection` at `0x180010006`
- `KERNEL32!LeaveCriticalSection` at `0x180010006`

## pseudocode

```c
__int64 __fastcall IASTL::IASComponentObject<NTEventLog>::GetProperty(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  LeaveCriticalSection(v1);
  return 2147614723LL;
}

```

## disassembly

```asm
0x18000fff0  push    rbx
0x18000fff2  sub     rsp, 20h
0x18000fff6  lea     rbx, [rcx+10h]
0x18000fffa  mov     rcx, rbx; lpCriticalSection
0x18000fffd  call    cs:__imp_EnterCriticalSection
0x180010003  mov     rcx, rbx; lpCriticalSection
0x180010006  call    cs:__imp_LeaveCriticalSection
0x18001000c  mov     eax, 80020003h
0x180010011  add     rsp, 20h
0x180010015  pop     rbx
0x180010016  retn
```
