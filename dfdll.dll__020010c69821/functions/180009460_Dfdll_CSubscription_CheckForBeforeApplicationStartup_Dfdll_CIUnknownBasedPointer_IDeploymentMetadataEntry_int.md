# Dfdll::CSubscription::CheckForBeforeApplicationStartup(Dfdll::CIUnknownBasedPointer<IDeploymentMetadataEntry> &,int &)

- ea: `0x180009460`
- end: `0x18000949c`
- name: `?CheckForBeforeApplicationStartup@CSubscription@Dfdll@@IEAAJAEAV?$CIUnknownBasedPointer@UIDeploymentMetadataEntry@@@2@AEAH@Z`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a2ac`

## callees

- `0x180009460`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CSubscription::CheckForBeforeApplicationStartup(__int64 a1, __int64 a2, int *a3)
{
  __int64 v3; // rcx
  __int64 result; // rax
  unsigned int v6; // [rsp+38h] [rbp+10h] BYREF

  v3 = *(_QWORD *)(a2 + 8);
  v6 = 0;
  result = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v3 + 64LL))(v3, &v6);
  if ( (int)result >= 0 )
  {
    *a3 = (v6 >> 2) & 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009460  push    rbx
0x180009462  sub     rsp, 20h
0x180009466  mov     rcx, [rdx+8]
0x18000946a  mov     rbx, r8
0x18000946d  and     [rsp+28h+arg_8], 0
0x180009472  lea     rdx, [rsp+28h+arg_8]
0x180009477  mov     rax, [rcx]
0x18000947a  mov     rax, [rax+40h]
0x18000947e  call    cs:__guard_dispatch_icall_fptr
0x180009484  test    eax, eax
0x180009486  js      short loc_180009496
0x180009488  mov     eax, [rsp+28h+arg_8]
0x18000948c  shr     eax, 2
0x18000948f  and     eax, 1
0x180009492  mov     [rbx], eax
0x180009494  xor     eax, eax
0x180009496  add     rsp, 20h
0x18000949a  pop     rbx
0x18000949b  retn
```
