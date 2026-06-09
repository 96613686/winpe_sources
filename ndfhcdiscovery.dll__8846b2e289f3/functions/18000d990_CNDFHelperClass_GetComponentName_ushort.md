# CNDFHelperClass::GetComponentName(ushort * *)

- ea: `0x18000d990`
- end: `0x18000da0d`
- name: `?GetComponentName@CNDFHelperClass@@UEAAJPEAPEAG@Z`
- size: `125`
- prototype: `__int64 __fastcall(CNDFHelperClass *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d990`
- `0x18000ebf8`
- `0x180011fcc`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000d9b5`
- `KERNEL32!EnterCriticalSection` at `0x18000d9b5`
- `KERNEL32!LeaveCriticalSection` at `0x18000d9d8`
- `KERNEL32!LeaveCriticalSection` at `0x18000d9eb`
- `KERNEL32!LeaveCriticalSection` at `0x18000d9d8`
- `KERNEL32!LeaveCriticalSection` at `0x18000d9eb`

## pseudocode

```c
int __fastcall CNDFHelperClass::GetComponentName(struct _RTL_CRITICAL_SECTION *this, unsigned __int16 **a2)
{
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  LSTATUS v6; // esi
  ResourceStringLoader *v7; // rcx

  if ( !a2 )
    return -2147024809;
  v5 = this + 8;
  EnterCriticalSection(this + 8);
  if ( HIDWORD(this[2].OwningThread) || (v6 = CNDFHelperClass::InitializeBaseData((CNDFHelperClass *)this), v6 >= 0) )
  {
    LeaveCriticalSection(v5);
    return ResourceStringLoader::LoadStringWithAlloc(v7, a2, &this[1].DebugInfo->Type);
  }
  else
  {
    LeaveCriticalSection(v5);
    return v6;
  }
}

```

## disassembly

```asm
0x18000d990  push    rbx
0x18000d992  push    rbp
0x18000d993  push    rsi
0x18000d994  push    rdi
0x18000d995  sub     rsp, 28h
0x18000d999  mov     rbp, rdx
0x18000d99c  mov     rbx, rcx
0x18000d99f  test    rdx, rdx
0x18000d9a2  jnz     short loc_18000D9AB
0x18000d9a4  mov     eax, 80070057h
0x18000d9a9  jmp     short loc_18000DA03
0x18000d9ab  lea     rdi, [rcx+140h]
0x18000d9b2  mov     rcx, rdi; lpCriticalSection
0x18000d9b5  call    cs:__imp_EnterCriticalSection
0x18000d9bc  nop     dword ptr [rax+rax+00h]
0x18000d9c1  cmp     dword ptr [rbx+64h], 0
0x18000d9c5  jnz     short loc_18000D9E8
0x18000d9c7  mov     rcx, rbx; this
0x18000d9ca  call    ?InitializeBaseData@CNDFHelperClass@@AEAAJXZ; CNDFHelperClass::InitializeBaseData(void)
0x18000d9cf  mov     esi, eax
0x18000d9d1  test    eax, eax
0x18000d9d3  jns     short loc_18000D9E8
0x18000d9d5  mov     rcx, rdi; lpCriticalSection
0x18000d9d8  call    cs:__imp_LeaveCriticalSection
0x18000d9df  nop     dword ptr [rax+rax+00h]
0x18000d9e4  mov     eax, esi
0x18000d9e6  jmp     short loc_18000DA03
0x18000d9e8  mov     rcx, rdi; lpCriticalSection
0x18000d9eb  call    cs:__imp_LeaveCriticalSection
0x18000d9f2  nop     dword ptr [rax+rax+00h]
0x18000d9f7  mov     r8, [rbx+28h]; unsigned __int16 *
0x18000d9fb  mov     rdx, rbp; unsigned __int16 **
0x18000d9fe  call    ?LoadStringWithAlloc@ResourceStringLoader@@QEAAJPEAPEAGPEBG@Z; ResourceStringLoader::LoadStringWithAlloc(ushort * *,ushort const *)
0x18000da03  add     rsp, 28h
0x18000da07  pop     rdi
0x18000da08  pop     rsi
0x18000da09  pop     rbp
0x18000da0a  pop     rbx
0x18000da0b  retn
```
