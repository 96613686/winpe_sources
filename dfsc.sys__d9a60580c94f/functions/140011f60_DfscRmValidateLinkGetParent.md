# DfscRmValidateLinkGetParent

- ea: `0x140011f60`
- end: `0x140011fd0`
- name: `DfscRmValidateLinkGetParent`
- size: `112`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140011f60`
- `0x14001cb40`
- `0x140023120`
- `0x140027310`

## pseudocode

```c
__int64 __fastcall DfscRmValidateLinkGetParent(__int64 a1)
{
  _QWORD *v1; // rdi
  int v3; // eax
  __int64 v4; // r8
  int v5; // r9d

  v1 = (_QWORD *)(a1 + 8);
  v3 = DfscRefCacheLookup(*(_QWORD *)a1, (const UNICODE_STRING *)(*(_QWORD *)a1 + 152LL), 0, (__int64 *)(a1 + 8));
  if ( v3 < 0
    || !(unsigned __int8)DfscReferralIsValid(*v1, *(unsigned int *)(*(_QWORD *)a1 + 232LL), v4, (unsigned int)v3) )
  {
    v5 = DfscValidateReferral(*(char **)a1, 1, v1);
  }
  *(_DWORD *)(a1 + 36) = v5;
  return ((v5 >> 31) & 0xFFFFFFFE) + 1;
}

```

## disassembly

```asm
0x140011f60  mov     [rsp+arg_0], rbx
0x140011f65  push    rdi
0x140011f66  sub     rsp, 20h
0x140011f6a  lea     rdi, [rcx+8]
0x140011f6e  mov     rbx, rcx
0x140011f71  mov     rcx, [rcx]
0x140011f74  mov     r9, rdi
0x140011f77  xor     r8d, r8d
0x140011f7a  lea     rdx, [rcx+98h]
0x140011f81  call    DfscRefCacheLookup
0x140011f86  mov     r9d, eax
0x140011f89  test    eax, eax
0x140011f8b  js      short loc_140011FA2
0x140011f8d  mov     rdx, [rbx]
0x140011f90  mov     rcx, [rdi]
0x140011f93  mov     edx, [rdx+0E8h]
0x140011f99  call    DfscReferralIsValid
0x140011f9e  test    al, al
0x140011fa0  jnz     short loc_140011FB5
0x140011fa2  mov     rcx, [rbx]
0x140011fa5  mov     r8, rdi
0x140011fa8  mov     edx, 1
0x140011fad  call    DfscValidateReferral
0x140011fb2  mov     r9d, eax
0x140011fb5  mov     eax, r9d
0x140011fb8  mov     [rbx+24h], r9d
0x140011fbc  mov     rbx, [rsp+28h+arg_0]
0x140011fc1  sar     eax, 1Fh
0x140011fc4  and     eax, 0FFFFFFFEh
0x140011fc7  inc     eax
0x140011fc9  add     rsp, 20h
0x140011fcd  pop     rdi
0x140011fce  retn
```
