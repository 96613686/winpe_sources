# PsmpApplyTimeCriticalTaskQuota

- ea: `0x18000f0bc`
- end: `0x18000f142`
- name: `PsmpApplyTimeCriticalTaskQuota`
- size: `134`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000eff0`
- `0x18001fb6c`

## callees

- `0x18000eef8`
- `0x18000f0bc`
- `0x18000f790`
- `0x180021bc4`

## pseudocode

```c
__int64 __fastcall PsmpApplyTimeCriticalTaskQuota(_DWORD *a1)
{
  __int64 result; // rax
  __int64 v3; // rdi
  __int64 SandboxedNetQuota; // rax
  int v5; // r9d

  for ( result = (unsigned int)a1[43]; a1[42] > (unsigned int)result; a1[43] = result )
  {
    v3 = 0;
    do
    {
      if ( (_DWORD)v3 )
        SandboxedNetQuota = PsmpQuerySandboxedNetQuota(a1);
      else
        SandboxedNetQuota = PsmpQuerySandboxedCycleTime(a1);
      if ( (PsmpQuotaTypeFlag[v3] & a1[32]) != 0 )
      {
        LOBYTE(v5) = 1;
        PsmpRequestAdditionalQuota((_DWORD)a1, 0, v3, v5, SandboxedNetQuota);
      }
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (int)v3 < 2 );
    result = (unsigned int)(a1[43] + 1);
  }
  return result;
}

```

## disassembly

```asm
0x18000f0bc  mov     [rsp+arg_0], rbx
0x18000f0c1  push    rdi
0x18000f0c2  sub     rsp, 30h
0x18000f0c6  mov     eax, [rcx+0ACh]
0x18000f0cc  mov     rbx, rcx
0x18000f0cf  cmp     [rcx+0A8h], eax
0x18000f0d5  ja      short loc_18000F0E2
0x18000f0d7  mov     rbx, [rsp+38h+arg_0]
0x18000f0dc  add     rsp, 30h
0x18000f0e0  pop     rdi
0x18000f0e1  retn
0x18000f0e2  xor     edi, edi
0x18000f0e4  mov     rcx, rbx
0x18000f0e7  test    edi, edi
0x18000f0e9  jz      short loc_18000F124
0x18000f0eb  call    PsmpQuerySandboxedNetQuota
0x18000f0f0  lea     rdx, PsmpQuotaTypeFlag
0x18000f0f7  mov     rcx, rax
0x18000f0fa  mov     eax, [rdx+rdi*4]
0x18000f0fd  test    [rbx+80h], eax
0x18000f103  jnz     short loc_18000F12B
0x18000f105  inc     edi
0x18000f107  cmp     edi, 2
0x18000f10a  jl      short loc_18000F0E4
0x18000f10c  mov     eax, [rbx+0ACh]
0x18000f112  inc     eax
0x18000f114  mov     [rbx+0ACh], eax
0x18000f11a  cmp     [rbx+0A8h], eax
0x18000f120  jbe     short loc_18000F0D7
0x18000f122  jmp     short loc_18000F0E2
0x18000f124  call    PsmpQuerySandboxedCycleTime
0x18000f129  jmp     short loc_18000F0F0
0x18000f12b  mov     [rsp+38h+var_18], rcx
0x18000f130  mov     r9b, 1
0x18000f133  mov     rcx, rbx
0x18000f136  mov     r8d, edi
0x18000f139  xor     edx, edx
0x18000f13b  call    PsmpRequestAdditionalQuota
0x18000f140  jmp     short loc_18000F105
```
