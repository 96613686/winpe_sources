# PnpReadDeviceConfiguration

- ea: `0x140ae0bb4`
- end: `0x140ae0ce2`
- name: `PnpReadDeviceConfiguration`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1408e45a4`

## callees

- `0x1406f4480`
- `0x14097499c`
- `0x140ae0bb4`
- `0x140bae410`
- `0x140bae8e0`

## string_xrefs

- `0x140ae0bf4`: `BootConfig`
- `0x140ae0c06`: `AllocConfig`
- `0x140ae0bfd`: `ForcedConfig`

## pseudocode

```c
__int64 __fastcall PnpReadDeviceConfiguration(void *a1, int a2, void **a3, _DWORD *a4)
{
  int v6; // edx
  int v7; // edx
  int RegistryValue; // edi
  __int64 Pool2; // rax
  unsigned int *v11; // r10
  unsigned int v12; // r8d
  __int64 i; // rax
  unsigned int v14; // r9d
  __int64 v15; // rcx
  unsigned int j; // edx
  __int64 v17; // rax

  *a3 = 0;
  *a4 = 0;
  v6 = a2 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 != 2 )
        return 3221225712LL;
    }
  }
  RegistryValue = IopGetRegistryValue(a1);
  if ( RegistryValue >= 0 )
  {
    if ( MEMORY[4] == 8 )
    {
      if ( MEMORY[0xC] )
      {
        Pool2 = ExAllocatePool2(256, MEMORY[0xC], 913337936);
        *a3 = (void *)Pool2;
        if ( Pool2 )
        {
          *a4 = MEMORY[0xC];
          memmove(*a3, (const void *)MEMORY[8], MEMORY[0xC]);
          v11 = (unsigned int *)*a3;
          v12 = 0;
          for ( i = (__int64)*a3 + 4; v12 < *v11; i = v15 )
          {
            if ( *(_DWORD *)i == -1 )
              *(_QWORD *)i = 1;
            v14 = *(_DWORD *)(i + 12);
            v15 = i + 16;
            for ( j = 0; j < v14; v15 += v17 + 20 )
            {
              v17 = 0;
              if ( *(_BYTE *)v15 == 5 )
                v17 = *(unsigned int *)(v15 + 4);
              ++j;
            }
            ++v12;
          }
        }
        else
        {
          RegistryValue = -1073741670;
        }
      }
    }
    else
    {
      RegistryValue = -1073741823;
    }
    ExFreePoolWithTag(0, 0);
  }
  return (unsigned int)RegistryValue;
}

```

## disassembly

```asm
0x140ae0bb4  push    rbx
0x140ae0bb6  push    rsi
0x140ae0bb7  push    rdi
0x140ae0bb8  push    r14
0x140ae0bba  sub     rsp, 28h
0x140ae0bbe  mov     qword ptr [r8], 0
0x140ae0bc5  mov     r14, r9
0x140ae0bc8  mov     dword ptr [r9], 0
0x140ae0bcf  mov     rsi, r8
0x140ae0bd2  mov     [rsp+48h+P], 0
0x140ae0bdb  sub     edx, 1
0x140ae0bde  jz      short loc_140AE0C06
0x140ae0be0  sub     edx, 1
0x140ae0be3  jz      short loc_140AE0BFD
0x140ae0be5  cmp     edx, 2
0x140ae0be8  jz      short loc_140AE0BF4
0x140ae0bea  mov     eax, 0C00000F0h
0x140ae0bef  jmp     loc_140AE0CD7
0x140ae0bf4  lea     rdx, aBootconfig; "BootConfig"
0x140ae0bfb  jmp     short loc_140AE0C0D
0x140ae0bfd  lea     rdx, aForcedconfig; "ForcedConfig"
0x140ae0c04  jmp     short loc_140AE0C0D
0x140ae0c06  lea     rdx, aAllocconfig; "AllocConfig"
0x140ae0c0d  lea     r9, [rsp+48h+P]
0x140ae0c12  xor     r8d, r8d
0x140ae0c15  call    IopGetRegistryValue
0x140ae0c1a  mov     edi, eax
0x140ae0c1c  test    eax, eax
0x140ae0c1e  js      loc_140AE0CD5
0x140ae0c24  mov     rbx, [rsp+48h+P]
0x140ae0c29  cmp     dword ptr [rbx+4], 8
0x140ae0c2d  jnz     loc_140AE0CC6
0x140ae0c33  mov     eax, [rbx+0Ch]
0x140ae0c36  test    eax, eax
0x140ae0c38  jz      loc_140AE0CCB
0x140ae0c3e  mov     edx, eax
0x140ae0c40  mov     ecx, 100h
0x140ae0c45  mov     r8d, 36706E50h
0x140ae0c4b  call    ExAllocatePool2
0x140ae0c50  mov     [rsi], rax
0x140ae0c53  test    rax, rax
0x140ae0c56  jz      short loc_140AE0CBF
0x140ae0c58  mov     eax, [rbx+0Ch]
0x140ae0c5b  mov     [r14], eax
0x140ae0c5e  mov     edx, [rbx+8]
0x140ae0c61  mov     r8d, [rbx+0Ch]; Size
0x140ae0c65  add     rdx, rbx; Src
0x140ae0c68  mov     rcx, [rsi]; void *
0x140ae0c6b  call    memmove
0x140ae0c70  mov     r10, [rsi]
0x140ae0c73  xor     r8d, r8d
0x140ae0c76  lea     rax, [r10+4]
0x140ae0c7a  cmp     [r10], r8d
0x140ae0c7d  jbe     short loc_140AE0CCB
0x140ae0c7f  cmp     dword ptr [rax], 0FFFFFFFFh
0x140ae0c82  jnz     short loc_140AE0C8B
0x140ae0c84  mov     qword ptr [rax], 1
0x140ae0c8b  mov     r9d, [rax+0Ch]
0x140ae0c8f  lea     rcx, [rax+10h]
0x140ae0c93  xor     edx, edx
0x140ae0c95  test    r9d, r9d
0x140ae0c98  jz      short loc_140AE0CB2
0x140ae0c9a  xor     eax, eax
0x140ae0c9c  cmp     byte ptr [rcx], 5
0x140ae0c9f  jnz     short loc_140AE0CA4
0x140ae0ca1  mov     eax, [rcx+4]
0x140ae0ca4  add     rcx, 14h
0x140ae0ca8  inc     edx
0x140ae0caa  add     rcx, rax
0x140ae0cad  cmp     edx, r9d
0x140ae0cb0  jb      short loc_140AE0C9A
0x140ae0cb2  inc     r8d
0x140ae0cb5  mov     rax, rcx
0x140ae0cb8  cmp     r8d, [r10]
0x140ae0cbb  jb      short loc_140AE0C7F
0x140ae0cbd  jmp     short loc_140AE0CCB
0x140ae0cbf  mov     edi, 0C000009Ah
0x140ae0cc4  jmp     short loc_140AE0CCB
0x140ae0cc6  mov     edi, 0C0000001h
0x140ae0ccb  xor     edx, edx; Tag
0x140ae0ccd  mov     rcx, rbx; P
0x140ae0cd0  call    ExFreePoolWithTag
0x140ae0cd5  mov     eax, edi
0x140ae0cd7  add     rsp, 28h
0x140ae0cdb  pop     r14
0x140ae0cdd  pop     rdi
0x140ae0cde  pop     rsi
0x140ae0cdf  pop     rbx
0x140ae0ce0  retn
```
