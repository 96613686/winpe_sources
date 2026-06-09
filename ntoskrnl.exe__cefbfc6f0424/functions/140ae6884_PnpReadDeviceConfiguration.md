# PnpReadDeviceConfiguration

- ea: `0x140ae6884`
- end: `0x140ae69b2`
- name: `PnpReadDeviceConfiguration`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140919364`

## callees

- `0x1406f6f80`
- `0x14087852c`
- `0x140ae6884`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x140ae68c4`: `BootConfig`
- `0x140ae68d6`: `AllocConfig`
- `0x140ae68cd`: `ForcedConfig`

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
0x140ae6884  push    rbx
0x140ae6886  push    rsi
0x140ae6887  push    rdi
0x140ae6888  push    r14
0x140ae688a  sub     rsp, 28h
0x140ae688e  mov     qword ptr [r8], 0
0x140ae6895  mov     r14, r9
0x140ae6898  mov     dword ptr [r9], 0
0x140ae689f  mov     rsi, r8
0x140ae68a2  mov     [rsp+48h+P], 0
0x140ae68ab  sub     edx, 1
0x140ae68ae  jz      short loc_140AE68D6
0x140ae68b0  sub     edx, 1
0x140ae68b3  jz      short loc_140AE68CD
0x140ae68b5  cmp     edx, 2
0x140ae68b8  jz      short loc_140AE68C4
0x140ae68ba  mov     eax, 0C00000F0h
0x140ae68bf  jmp     loc_140AE69A7
0x140ae68c4  lea     rdx, aBootconfig; "BootConfig"
0x140ae68cb  jmp     short loc_140AE68DD
0x140ae68cd  lea     rdx, aForcedconfig; "ForcedConfig"
0x140ae68d4  jmp     short loc_140AE68DD
0x140ae68d6  lea     rdx, aAllocconfig; "AllocConfig"
0x140ae68dd  lea     r9, [rsp+48h+P]
0x140ae68e2  xor     r8d, r8d
0x140ae68e5  call    IopGetRegistryValue
0x140ae68ea  mov     edi, eax
0x140ae68ec  test    eax, eax
0x140ae68ee  js      loc_140AE69A5
0x140ae68f4  mov     rbx, [rsp+48h+P]
0x140ae68f9  cmp     dword ptr [rbx+4], 8
0x140ae68fd  jnz     loc_140AE6996
0x140ae6903  mov     eax, [rbx+0Ch]
0x140ae6906  test    eax, eax
0x140ae6908  jz      loc_140AE699B
0x140ae690e  mov     edx, eax
0x140ae6910  mov     ecx, 100h
0x140ae6915  mov     r8d, 36706E50h
0x140ae691b  call    ExAllocatePool2
0x140ae6920  mov     [rsi], rax
0x140ae6923  test    rax, rax
0x140ae6926  jz      short loc_140AE698F
0x140ae6928  mov     eax, [rbx+0Ch]
0x140ae692b  mov     [r14], eax
0x140ae692e  mov     edx, [rbx+8]
0x140ae6931  mov     r8d, [rbx+0Ch]; Size
0x140ae6935  add     rdx, rbx; Src
0x140ae6938  mov     rcx, [rsi]; void *
0x140ae693b  call    memmove
0x140ae6940  mov     r10, [rsi]
0x140ae6943  xor     r8d, r8d
0x140ae6946  lea     rax, [r10+4]
0x140ae694a  cmp     [r10], r8d
0x140ae694d  jbe     short loc_140AE699B
0x140ae694f  cmp     dword ptr [rax], 0FFFFFFFFh
0x140ae6952  jnz     short loc_140AE695B
0x140ae6954  mov     qword ptr [rax], 1
0x140ae695b  mov     r9d, [rax+0Ch]
0x140ae695f  lea     rcx, [rax+10h]
0x140ae6963  xor     edx, edx
0x140ae6965  test    r9d, r9d
0x140ae6968  jz      short loc_140AE6982
0x140ae696a  xor     eax, eax
0x140ae696c  cmp     byte ptr [rcx], 5
0x140ae696f  jnz     short loc_140AE6974
0x140ae6971  mov     eax, [rcx+4]
0x140ae6974  add     rcx, 14h
0x140ae6978  inc     edx
0x140ae697a  add     rcx, rax
0x140ae697d  cmp     edx, r9d
0x140ae6980  jb      short loc_140AE696A
0x140ae6982  inc     r8d
0x140ae6985  mov     rax, rcx
0x140ae6988  cmp     r8d, [r10]
0x140ae698b  jb      short loc_140AE694F
0x140ae698d  jmp     short loc_140AE699B
0x140ae698f  mov     edi, 0C000009Ah
0x140ae6994  jmp     short loc_140AE699B
0x140ae6996  mov     edi, 0C0000001h
0x140ae699b  xor     edx, edx; Tag
0x140ae699d  mov     rcx, rbx; P
0x140ae69a0  call    ExFreePoolWithTag
0x140ae69a5  mov     eax, edi
0x140ae69a7  add     rsp, 28h
0x140ae69ab  pop     r14
0x140ae69ad  pop     rdi
0x140ae69ae  pop     rsi
0x140ae69af  pop     rbx
0x140ae69b0  retn
```
