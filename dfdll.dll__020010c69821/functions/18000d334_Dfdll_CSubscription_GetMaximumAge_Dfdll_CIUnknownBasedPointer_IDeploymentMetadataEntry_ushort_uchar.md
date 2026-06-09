# Dfdll::CSubscription::GetMaximumAge(Dfdll::CIUnknownBasedPointer<IDeploymentMetadataEntry> &,ushort &,uchar &)

- ea: `0x18000d334`
- end: `0x18000d39f`
- name: `?GetMaximumAge@CSubscription@Dfdll@@IEAAJAEAV?$CIUnknownBasedPointer@UIDeploymentMetadataEntry@@@2@AEAGAEAE@Z`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009c44`

## callees

- `0x18000d334`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CSubscription::GetMaximumAge(__int64 a1, __int64 a2, _WORD *a3, _BYTE *a4)
{
  __int64 result; // rax

  *a3 = 0;
  *a4 = 0;
  result = (*(__int64 (__fastcall **)(_QWORD, _WORD *))(**(_QWORD **)(a2 + 8) + 48LL))(*(_QWORD *)(a2 + 8), a3);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a2 + 8) + 56LL))(*(_QWORD *)(a2 + 8), a4);
    if ( (int)result >= 0 )
      return *a4 == 0 ? 0x8007054F : 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000d334  mov     [rsp+arg_0], rbx
0x18000d339  mov     [rsp+arg_8], rsi
0x18000d33e  push    rdi
0x18000d33f  sub     rsp, 20h
0x18000d343  xor     esi, esi
0x18000d345  mov     rdi, rdx
0x18000d348  mov     [r8], si
0x18000d34c  mov     rbx, r9
0x18000d34f  mov     [r9], sil
0x18000d352  mov     rcx, [rdx+8]
0x18000d356  mov     rdx, r8
0x18000d359  mov     rax, [rcx]
0x18000d35c  mov     rax, [rax+30h]
0x18000d360  call    cs:__guard_dispatch_icall_fptr
0x18000d366  test    eax, eax
0x18000d368  js      short loc_18000D38F
0x18000d36a  mov     rcx, [rdi+8]
0x18000d36e  mov     rdx, rbx
0x18000d371  mov     rax, [rcx]
0x18000d374  mov     rax, [rax+38h]
0x18000d378  call    cs:__guard_dispatch_icall_fptr
0x18000d37e  test    eax, eax
0x18000d380  js      short loc_18000D38F
0x18000d382  mov     al, [rbx]
0x18000d384  neg     al
0x18000d386  sbb     eax, eax
0x18000d388  not     eax
0x18000d38a  and     eax, 8007054Fh
0x18000d38f  mov     rbx, [rsp+28h+arg_0]
0x18000d394  mov     rsi, [rsp+28h+arg_8]
0x18000d399  add     rsp, 20h
0x18000d39d  pop     rdi
0x18000d39e  retn
```
