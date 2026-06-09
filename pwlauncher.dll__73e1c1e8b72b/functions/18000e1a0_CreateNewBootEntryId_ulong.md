# CreateNewBootEntryId(ulong *)

- ea: `0x18000e1a0`
- end: `0x18000e428`
- name: `?CreateNewBootEntryId@@YAJPEAK@Z`
- size: `648`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005c98`

## callees

- `0x180008ac8`
- `0x180008af0`
- `0x18000e1a0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000e227`
- `KERNEL32!GetProcessHeap` at `0x18000e2c0`
- `KERNEL32!GetProcessHeap` at `0x18000e3e6`
- `KERNEL32!GetProcessHeap` at `0x18000e3ff`
- `KERNEL32!GetProcessHeap` at `0x18000e227`
- `KERNEL32!GetProcessHeap` at `0x18000e2c0`
- `KERNEL32!GetProcessHeap` at `0x18000e3e6`
- `KERNEL32!GetProcessHeap` at `0x18000e3ff`
- `KERNEL32!HeapAlloc` at `0x18000e235`
- `KERNEL32!HeapAlloc` at `0x18000e2d3`
- `KERNEL32!HeapAlloc` at `0x18000e235`
- `KERNEL32!HeapAlloc` at `0x18000e2d3`
- `KERNEL32!HeapFree` at `0x18000e3f4`
- `KERNEL32!HeapFree` at `0x18000e40d`
- `KERNEL32!HeapFree` at `0x18000e3f4`
- `KERNEL32!HeapFree` at `0x18000e40d`
- `ntdll!NtEnumerateBootEntries` at `0x18000e211`
- `ntdll!NtEnumerateBootEntries` at `0x18000e276`
- `ntdll!NtEnumerateBootEntries` at `0x18000e211`
- `ntdll!NtEnumerateBootEntries` at `0x18000e276`
- `ntdll!RtlInitializeBitMap` at `0x18000e32a`
- `ntdll!RtlInitializeBitMap` at `0x18000e32a`
- `ntdll!RtlFindClearBits` at `0x18000e3a6`
- `ntdll!RtlFindClearBits` at `0x18000e3a6`
- `ntdll!RtlSetBit` at `0x18000e381`
- `ntdll!RtlSetBit` at `0x18000e381`

## pseudocode

```c
__int64 __fastcall CreateNewBootEntryId(unsigned int *a1)
{
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  unsigned int *v5; // rsi
  ULONG v6; // ebx
  HANDLE v7; // rax
  unsigned int *v8; // rax
  HANDLE ProcessHeap; // rax
  ULONG *v10; // rax
  ULONG *v11; // rbp
  unsigned int *v12; // rbx
  _QWORD *v13; // rcx
  ULONG v14; // edx
  ULONG ClearBits; // eax
  HANDLE v16; // rax
  HANDLE v17; // rax
  _RTL_BITMAP BitMapHeader; // [rsp+20h] [rbp-28h] BYREF
  ULONG BufferLength; // [rsp+50h] [rbp+8h] BYREF

  BufferLength = 0;
  BitMapHeader = 0;
  if ( !a1 )
  {
    v2 = -1073741811;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 10;
LABEL_5:
      WPP_SF_(v3[2], v4, &WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids);
      return v2;
    }
    return v2;
  }
  v5 = 0;
  v2 = NtEnumerateBootEntries(0, &BufferLength);
  if ( v2 != -1073741789 )
  {
LABEL_12:
    if ( (v2 & 0x80000000) == 0 )
    {
      ProcessHeap = GetProcessHeap();
      v10 = (ULONG *)HeapAlloc(ProcessHeap, 8u, 0x2001u);
      v11 = v10;
      if ( v10 )
      {
        RtlInitializeBitMap(&BitMapHeader, v10, 0x2001u);
        v12 = v5;
        if ( v5 )
        {
          v13 = WPP_GLOBAL_Control;
          do
          {
            if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 )
            {
              WPP_SF_d(v13[2], 14, &WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids, v12[3]);
              v13 = WPP_GLOBAL_Control;
            }
            v14 = v12[3];
            if ( v14 <= 0xFFFF )
            {
              RtlSetBit(&BitMapHeader, v14);
              v13 = WPP_GLOBAL_Control;
            }
            if ( !*v12 )
              break;
            v12 = (unsigned int *)((char *)v12 + *v12);
          }
          while ( v12 );
        }
        ClearBits = RtlFindClearBits(&BitMapHeader, 1u, 0);
        *a1 = ClearBits;
        if ( ClearBits <= 0xFFFF )
        {
          v2 = 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids);
          v2 = -1073741823;
        }
        v16 = GetProcessHeap();
        HeapFree(v16, 0, v11);
      }
      else
      {
        v2 = -1073741801;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids, v2);
    }
    if ( v5 )
    {
      v17 = GetProcessHeap();
      HeapFree(v17, 0, v5);
    }
    return v2;
  }
  v6 = BufferLength;
  v7 = GetProcessHeap();
  v8 = (unsigned int *)HeapAlloc(v7, 8u, v6);
  v5 = v8;
  if ( v8 )
  {
    v2 = NtEnumerateBootEntries(v8, &BufferLength);
    goto LABEL_12;
  }
  v2 = -1073741801;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v4 = 11;
    goto LABEL_5;
  }
  return v2;
}

```

## disassembly

```asm
0x18000e1a0  mov     rax, rsp
0x18000e1a3  mov     [rax+18h], rbx
0x18000e1a7  mov     [rax+20h], rbp
0x18000e1ab  push    rsi
0x18000e1ac  push    rdi
0x18000e1ad  push    r14
0x18000e1af  sub     rsp, 30h
0x18000e1b3  mov     dword ptr [rax+8], 0
0x18000e1ba  xorps   xmm0, xmm0
0x18000e1bd  mov     r14, rcx
0x18000e1c0  movups  xmmword ptr [rax-28h], xmm0
0x18000e1c4  test    rcx, rcx
0x18000e1c7  jnz     short loc_18000E208
0x18000e1c9  mov     ebx, 0C000000Dh
0x18000e1ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1d5  lea     rdi, WPP_GLOBAL_Control
0x18000e1dc  cmp     rcx, rdi
0x18000e1df  jz      loc_18000E413
0x18000e1e5  test    byte ptr [rcx+1Ch], 1
0x18000e1e9  jz      loc_18000E413
0x18000e1ef  lea     edx, [r14+0Ah]
0x18000e1f3  mov     rcx, [rcx+10h]
0x18000e1f7  lea     r8, WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids
0x18000e1fe  call    WPP_SF_
0x18000e203  jmp     loc_18000E413
0x18000e208  lea     rdx, [rsp+48h+BufferLength]; BufferLength
0x18000e20d  xor     ecx, ecx; Buffer
0x18000e20f  xor     esi, esi
0x18000e211  call    cs:__imp_NtEnumerateBootEntries
0x18000e217  lea     edi, [rsi+8]
0x18000e21a  mov     ebx, eax
0x18000e21c  cmp     eax, 0C0000023h
0x18000e221  jnz     short loc_18000E27E
0x18000e223  mov     ebx, [rsp+48h+BufferLength]
0x18000e227  call    cs:__imp_GetProcessHeap
0x18000e22d  mov     r8d, ebx; dwBytes
0x18000e230  mov     edx, edi; dwFlags
0x18000e232  mov     rcx, rax; hHeap
0x18000e235  call    cs:__imp_HeapAlloc
0x18000e23b  mov     rsi, rax
0x18000e23e  test    rax, rax
0x18000e241  jnz     short loc_18000E26E
0x18000e243  mov     ebx, 0C0000017h
0x18000e248  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e24f  lea     rdi, WPP_GLOBAL_Control
0x18000e256  cmp     rcx, rdi
0x18000e259  jz      loc_18000E413
0x18000e25f  test    byte ptr [rcx+1Ch], 1
0x18000e263  jz      loc_18000E413
0x18000e269  lea     edx, [rax+0Bh]
0x18000e26c  jmp     short loc_18000E1F3
0x18000e26e  lea     rdx, [rsp+48h+BufferLength]; BufferLength
0x18000e273  mov     rcx, rax; Buffer
0x18000e276  call    cs:__imp_NtEnumerateBootEntries
0x18000e27c  mov     ebx, eax
0x18000e27e  test    ebx, ebx
0x18000e280  jns     short loc_18000E2C0
0x18000e282  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e289  lea     rdi, WPP_GLOBAL_Control
0x18000e290  cmp     rcx, rdi
0x18000e293  jz      loc_18000E3FA
0x18000e299  test    byte ptr [rcx+1Ch], 1
0x18000e29d  jz      loc_18000E3FA
0x18000e2a3  mov     rcx, [rcx+10h]
0x18000e2a7  lea     r8, WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids
0x18000e2ae  mov     edx, 0Ch
0x18000e2b3  mov     r9d, ebx
0x18000e2b6  call    WPP_SF_d
0x18000e2bb  jmp     loc_18000E3FA
0x18000e2c0  call    cs:__imp_GetProcessHeap
0x18000e2c6  mov     ebx, 2001h
0x18000e2cb  mov     edx, edi; dwFlags
0x18000e2cd  mov     rcx, rax; hHeap
0x18000e2d0  mov     r8d, ebx; dwBytes
0x18000e2d3  call    cs:__imp_HeapAlloc
0x18000e2d9  mov     rbp, rax
0x18000e2dc  test    rax, rax
0x18000e2df  jnz     short loc_18000E31F
0x18000e2e1  mov     ebx, 0C0000017h
0x18000e2e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2ed  lea     rdi, WPP_GLOBAL_Control
0x18000e2f4  cmp     rcx, rdi
0x18000e2f7  jz      loc_18000E3FA
0x18000e2fd  test    byte ptr [rcx+1Ch], 1
0x18000e301  jz      loc_18000E3FA
0x18000e307  mov     rcx, [rcx+10h]
0x18000e30b  lea     edx, [rax+0Dh]
0x18000e30e  lea     r8, WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids
0x18000e315  call    WPP_SF_
0x18000e31a  jmp     loc_18000E3FA
0x18000e31f  mov     r8d, ebx; SizeOfBitMap
0x18000e322  lea     rcx, [rsp+48h+BitMapHeader]; BitMapHeader
0x18000e327  mov     rdx, rbp; BitMapBuffer
0x18000e32a  call    cs:__imp_RtlInitializeBitMap
0x18000e330  lea     rdi, WPP_GLOBAL_Control
0x18000e337  mov     rbx, rsi
0x18000e33a  test    rsi, rsi
0x18000e33d  jz      short loc_18000E39A
0x18000e33f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e346  cmp     rcx, rdi
0x18000e349  jz      short loc_18000E371
0x18000e34b  test    byte ptr [rcx+1Ch], 4
0x18000e34f  jz      short loc_18000E371
0x18000e351  mov     r9d, [rbx+0Ch]
0x18000e355  lea     r8, WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids
0x18000e35c  mov     rcx, [rcx+10h]
0x18000e360  mov     edx, 0Eh
0x18000e365  call    WPP_SF_d
0x18000e36a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e371  mov     edx, [rbx+0Ch]; BitNumber
0x18000e374  cmp     edx, 0FFFFh
0x18000e37a  ja      short loc_18000E38E
0x18000e37c  lea     rcx, [rsp+48h+BitMapHeader]; BitMapHeader
0x18000e381  call    cs:__imp_RtlSetBit
0x18000e387  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e38e  cmp     dword ptr [rbx], 0
0x18000e391  jz      short loc_18000E39A
0x18000e393  mov     eax, [rbx]
0x18000e395  add     rbx, rax
0x18000e398  jnz     short loc_18000E346
0x18000e39a  xor     r8d, r8d; HintIndex
0x18000e39d  lea     rcx, [rsp+48h+BitMapHeader]; BitMapHeader
0x18000e3a2  lea     edx, [r8+1]; NumberToFind
0x18000e3a6  call    cs:__imp_RtlFindClearBits
0x18000e3ac  mov     [r14], eax
0x18000e3af  cmp     eax, 0FFFFh
0x18000e3b4  jbe     short loc_18000E3E4
0x18000e3b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3bd  cmp     rcx, rdi
0x18000e3c0  jz      short loc_18000E3DD
0x18000e3c2  test    byte ptr [rcx+1Ch], 1
0x18000e3c6  jz      short loc_18000E3DD
0x18000e3c8  mov     rcx, [rcx+10h]
0x18000e3cc  lea     r8, WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids
0x18000e3d3  mov     edx, 0Fh
0x18000e3d8  call    WPP_SF_
0x18000e3dd  mov     ebx, 0C0000001h
0x18000e3e2  jmp     short loc_18000E3E6
0x18000e3e4  xor     ebx, ebx
0x18000e3e6  call    cs:__imp_GetProcessHeap
0x18000e3ec  mov     r8, rbp; lpMem
0x18000e3ef  xor     edx, edx; dwFlags
0x18000e3f1  mov     rcx, rax; hHeap
0x18000e3f4  call    cs:__imp_HeapFree
0x18000e3fa  test    rsi, rsi
0x18000e3fd  jz      short loc_18000E413
0x18000e3ff  call    cs:__imp_GetProcessHeap
0x18000e405  mov     r8, rsi; lpMem
0x18000e408  xor     edx, edx; dwFlags
0x18000e40a  mov     rcx, rax; hHeap
0x18000e40d  call    cs:__imp_HeapFree
0x18000e413  mov     rbp, [rsp+48h+arg_18]
0x18000e418  mov     eax, ebx
0x18000e41a  mov     rbx, [rsp+48h+arg_10]
0x18000e41f  add     rsp, 30h
0x18000e423  pop     r14
0x18000e425  pop     rdi
0x18000e426  pop     rsi
0x18000e427  retn
```
