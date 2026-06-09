# ATL::CComClassFactory::~CComClassFactory(void)

- ea: `0x18000e13c`
- end: `0x18000e159`
- name: `??1CComClassFactory@ATL@@QEAA@XZ`
- size: `29`
- prototype: `void __fastcall(ATL::CComClassFactory *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800139f9`

## callees

- `0x18000e13c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000e14e`
- `KERNEL32!DeleteCriticalSection` at `0x18000e14e`

## pseudocode

```c
void __fastcall ATL::CComClassFactory::~CComClassFactory(ATL::CComClassFactory *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  if ( LOBYTE(v1[1].DebugInfo) )
  {
    LOBYTE(v1[1].DebugInfo) = 0;
    DeleteCriticalSection(v1);
  }
}

```

## disassembly

```asm
0x18000e13c  sub     rsp, 28h
0x18000e140  add     rcx, 10h; lpCriticalSection
0x18000e144  cmp     byte ptr [rcx+28h], 0
0x18000e148  jz      short loc_18000E154
0x18000e14a  mov     byte ptr [rcx+28h], 0
0x18000e14e  call    cs:__imp_DeleteCriticalSection
0x18000e154  add     rsp, 28h
0x18000e158  retn
```
