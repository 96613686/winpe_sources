# Wow64NtOpenKey

- ea: `0x18001d698`
- end: `0x18001d7a8`
- name: `Wow64NtOpenKey`
- size: `272`
- prototype: `__int64 __fastcall(HANDLE *, unsigned int, __int128 *, unsigned int, int KeySetInformation)`
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180017210`
- `0x180017688`
- `0x1800176d8`
- `0x18001782c`
- `0x180017b54`
- `0x1800181ec`
- `0x18001a410`
- `0x18001a710`
- `0x18001aad0`
- `0x18001c648`
- `0x18001ca9c`

## callees

- `0x1800035a0`
- `0x18001d698`

## import_xrefs

- `ntdll!NtClose` at `0x18001d789`
- `ntdll!NtClose` at `0x18001d789`
- `ntdll!RtlFreeHeap` at `0x18001d748`
- `ntdll!RtlFreeHeap` at `0x18001d748`
- `ntdll!NtOpenKeyEx` at `0x18001d728`
- `ntdll!NtOpenKeyEx` at `0x18001d728`
- `ntdll!NtSetInformationKey` at `0x18001d779`
- `ntdll!NtSetInformationKey` at `0x18001d779`

## pseudocode

```c
__int64 __fastcall Wow64NtOpenKey(HANDLE *a1, unsigned int a2, __int128 *a3, unsigned int a4, int KeySetInformation)
{
  __int128 v5; // xmm0
  __int128 v7; // xmm1
  __int128 v10; // xmm0
  __int64 result; // rax
  int v12; // ebx
  NTSTATUS v13; // edi
  HANDLE KeyHandle; // [rsp+30h] [rbp-21h] BYREF
  PVOID P; // [rsp+38h] [rbp-19h] BYREF
  __int64 v16; // [rsp+40h] [rbp-11h] BYREF
  __int16 v17; // [rsp+48h] [rbp-9h]
  char v18; // [rsp+4Ah] [rbp-7h]
  _OWORD v19[5]; // [rsp+50h] [rbp-1h] BYREF
  bool v20; // [rsp+C0h] [rbp+6Fh] BYREF

  v5 = *a3;
  v7 = a3[1];
  v16 = 0;
  v17 = 0;
  v18 = 0;
  KeyHandle = 0;
  v20 = 0;
  v19[0] = v5;
  P = 0;
  v10 = a3[2];
  KeySetInformation = 0;
  v19[2] = v10;
  v19[1] = v7;
  result = ConstructKernelKeyPath(
             a2,
             (__int64)v19,
             &KeySetInformation,
             (__int64)&v16,
             &v20,
             (struct _UNICODE_STRING **)&P);
  if ( (int)result >= 0 )
  {
    v12 = NtOpenKeyEx(&KeyHandle, a2, v19, a4);
    if ( P )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    if ( v12 >= 0 )
    {
      if ( v20 )
      {
        if ( KeySetInformation )
        {
          KeySetInformation &= 0xF01u;
          v13 = NtSetInformationKey(KeyHandle, KeySetHandleTagsInformation, &KeySetInformation, 4u);
          if ( v13 < 0 )
          {
            NtClose(KeyHandle);
            return (unsigned int)v13;
          }
        }
      }
      *a1 = KeyHandle;
    }
    return (unsigned int)v12;
  }
  return result;
}

```

## disassembly

```asm
0x18001d698  push    rbp
0x18001d69a  push    rbx
0x18001d69b  push    rsi
0x18001d69c  push    rdi
0x18001d69d  lea     rbp, [rsp-37h]
0x18001d6a2  sub     rsp, 88h
0x18001d6a9  movups  xmm0, xmmword ptr [r8]
0x18001d6ad  xor     eax, eax
0x18001d6af  mov     ebx, edx
0x18001d6b1  movups  xmm1, xmmword ptr [r8+10h]
0x18001d6b6  mov     [rbp+4Fh+var_60], rax
0x18001d6ba  lea     rdx, [rbp+4Fh+var_50]
0x18001d6be  mov     [rbp+4Fh+var_58], ax
0x18001d6c2  mov     edi, r9d
0x18001d6c5  mov     [rbp+4Fh+var_56], al
0x18001d6c8  lea     r9, [rbp+4Fh+var_60]
0x18001d6cc  mov     [rbp+4Fh+KeyHandle], rax
0x18001d6d0  mov     rsi, rcx
0x18001d6d3  mov     [rbp+4Fh+arg_10], al
0x18001d6d6  mov     ecx, ebx
0x18001d6d8  movups  [rbp+4Fh+var_50], xmm0
0x18001d6dc  lea     rax, [rbp+4Fh+P]
0x18001d6e0  mov     [rbp+4Fh+P], 0
0x18001d6e8  movups  xmm0, xmmword ptr [r8+20h]
0x18001d6ed  mov     [rsp+0A0h+var_78], rax
0x18001d6f2  lea     r8, [rbp+4Fh+KeySetInformation]
0x18001d6f6  lea     rax, [rbp+4Fh+arg_10]
0x18001d6fa  mov     [rbp+4Fh+KeySetInformation], 0
0x18001d701  movups  [rbp+4Fh+var_30], xmm0
0x18001d705  mov     [rsp+0A0h+var_80], rax
0x18001d70a  movups  [rbp+4Fh+var_40], xmm1
0x18001d70e  call    ConstructKernelKeyPath
0x18001d713  test    eax, eax
0x18001d715  js      loc_18001D79C
0x18001d71b  mov     r9d, edi
0x18001d71e  lea     r8, [rbp+4Fh+var_50]
0x18001d722  mov     edx, ebx
0x18001d724  lea     rcx, [rbp+4Fh+KeyHandle]
0x18001d728  call    cs:__imp_NtOpenKeyEx
0x18001d72e  mov     r8, [rbp+4Fh+P]; P
0x18001d732  mov     ebx, eax
0x18001d734  test    r8, r8
0x18001d737  jz      short loc_18001D74E
0x18001d739  mov     rcx, gs:60h
0x18001d742  xor     edx, edx; Flags
0x18001d744  mov     rcx, [rcx+30h]; HeapHandle
0x18001d748  call    cs:__imp_RtlFreeHeap
0x18001d74e  test    ebx, ebx
0x18001d750  js      short loc_18001D79A
0x18001d752  cmp     [rbp+4Fh+arg_10], 0
0x18001d756  jz      short loc_18001D793
0x18001d758  mov     eax, [rbp+4Fh+KeySetInformation]
0x18001d75b  test    eax, eax
0x18001d75d  jz      short loc_18001D793
0x18001d75f  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x18001d763  lea     r8, [rbp+4Fh+KeySetInformation]; KeySetInformation
0x18001d767  mov     r9d, 4; KeySetInformationLength
0x18001d76d  and     eax, 0F01h
0x18001d772  mov     [rbp+4Fh+KeySetInformation], eax
0x18001d775  lea     edx, [r9+1]; KeySetInformationClass
0x18001d779  call    cs:__imp_NtSetInformationKey
0x18001d77f  mov     edi, eax
0x18001d781  test    eax, eax
0x18001d783  jns     short loc_18001D793
0x18001d785  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x18001d789  call    cs:__imp_NtClose
0x18001d78f  mov     eax, edi
0x18001d791  jmp     short loc_18001D79C
0x18001d793  mov     rax, [rbp+4Fh+KeyHandle]
0x18001d797  mov     [rsi], rax
0x18001d79a  mov     eax, ebx
0x18001d79c  add     rsp, 88h
0x18001d7a3  pop     rdi
0x18001d7a4  pop     rsi
0x18001d7a5  pop     rbx
0x18001d7a6  pop     rbp
0x18001d7a7  retn
```
