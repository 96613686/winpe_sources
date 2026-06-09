# RemoveBootEntry(ulong)

- ea: `0x18000e6cc`
- end: `0x18000e913`
- name: `?RemoveBootEntry@@YAJK@Z`
- size: `583`
- prototype: `__int64 __fastcall(ULONG)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005c98`

## callees

- `0x180008ac8`
- `0x180008af0`
- `0x18000e6cc`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000e783`
- `KERNEL32!GetProcessHeap` at `0x18000e845`
- `KERNEL32!GetProcessHeap` at `0x18000e783`
- `KERNEL32!GetProcessHeap` at `0x18000e845`
- `KERNEL32!HeapAlloc` at `0x18000e794`
- `KERNEL32!HeapAlloc` at `0x18000e794`
- `KERNEL32!HeapFree` at `0x18000e853`
- `KERNEL32!HeapFree` at `0x18000e853`
- `ntdll!NtQueryBootEntryOrder` at `0x18000e73e`
- `ntdll!NtQueryBootEntryOrder` at `0x18000e7e3`
- `ntdll!NtQueryBootEntryOrder` at `0x18000e73e`
- `ntdll!NtQueryBootEntryOrder` at `0x18000e7e3`
- `ntdll!NtSetBootEntryOrder` at `0x18000e8dc`
- `ntdll!NtSetBootEntryOrder` at `0x18000e8dc`
- `ntdll!NtDeleteBootEntry` at `0x18000e6e8`
- `ntdll!NtDeleteBootEntry` at `0x18000e6e8`

## pseudocode

```c
__int64 __fastcall RemoveBootEntry(ULONG a1)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  ULONG *v6; // rsi
  SIZE_T v7; // rbx
  HANDLE ProcessHeap; // rax
  ULONG *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rcx
  HANDLE v13; // rax
  ULONG *v15; // rdx
  __int64 v16; // r8
  NTSTATUS v17; // eax
  ULONG Count; // [rsp+48h] [rbp+10h] BYREF

  Count = 0;
  v2 = NtDeleteBootEntry(a1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v6 = 0;
    v2 = NtQueryBootEntryOrder(0, &Count);
    v3 = v2;
    if ( v2 < 0 )
    {
      if ( v2 != -1073741789 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v3;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_30;
        v5 = 42;
        goto LABEL_5;
      }
      v7 = 4LL * Count;
      ProcessHeap = GetProcessHeap();
      v9 = (ULONG *)HeapAlloc(ProcessHeap, 8u, v7);
      v6 = v9;
      if ( !v9 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids);
          v4 = WPP_GLOBAL_Control;
        }
        v3 = -1073741801;
        goto LABEL_30;
      }
      v3 = NtQueryBootEntryOrder(v9, &Count);
    }
    if ( (v3 & 0x80000000) == 0 )
    {
      v12 = 0;
      if ( !Count )
        goto LABEL_25;
      while ( v6[v12] != a1 )
      {
        v12 = (unsigned int)(v12 + 1);
        if ( (unsigned int)v12 >= Count )
          goto LABEL_25;
      }
      if ( (_DWORD)v12 == -1 )
        goto LABEL_25;
      v15 = (ULONG *)(Count - 1);
      if ( (unsigned int)v12 < (unsigned int)v15 )
      {
        do
        {
          v16 = (unsigned int)(v12 + 1);
          v6[v12] = v6[v16];
          v12 = v16;
        }
        while ( (unsigned int)v16 < (unsigned int)v15 );
      }
      v17 = NtSetBootEntryOrder(v6, v15);
      v3 = v17;
      if ( v17 >= 0 )
      {
LABEL_25:
        v3 = 0;
        goto LABEL_26;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_27;
      v10 = 45;
      v11 = (unsigned int)v17;
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_27;
      v10 = 44;
      v11 = v3;
    }
    WPP_SF_d(v4[2], v10, &WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids, v11);
LABEL_26:
    v4 = WPP_GLOBAL_Control;
LABEL_27:
    if ( !v6 )
      goto LABEL_30;
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v6);
    goto LABEL_29;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v5 = 41;
LABEL_5:
    WPP_SF_d(v4[2], v5, &WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids, (unsigned int)v2);
LABEL_29:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_30:
  if ( v4 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v4 + 28) & 4) != 0 )
    {
      WPP_SF_d(v4[2], 46, &WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids, v3);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
      WPP_SF_(v4[2], 47, &WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids);
  }
  return v3;
}

```

## disassembly

```asm
0x18000e6cc  mov     [rsp+arg_0], rbx
0x18000e6d1  mov     [rsp+arg_10], rbp
0x18000e6d6  push    rsi
0x18000e6d7  push    rdi
0x18000e6d8  push    r14
0x18000e6da  sub     rsp, 20h
0x18000e6de  mov     ebp, ecx
0x18000e6e0  mov     [rsp+38h+Count], 0
0x18000e6e8  call    cs:__imp_NtDeleteBootEntry
0x18000e6ee  lea     r14, WPP_bd0f4676a9f4383708ca911f37b6c87c_Traceguids
0x18000e6f5  mov     ebx, eax
0x18000e6f7  test    eax, eax
0x18000e6f9  jns     short loc_18000E735
0x18000e6fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e702  lea     rdi, WPP_GLOBAL_Control
0x18000e709  cmp     rcx, rdi
0x18000e70c  jz      loc_18000E8A2
0x18000e712  test    byte ptr [rcx+1Ch], 1
0x18000e716  jz      loc_18000E860
0x18000e71c  mov     edx, 29h ; ')'
0x18000e721  mov     rcx, [rcx+10h]
0x18000e725  mov     r9d, eax
0x18000e728  mov     r8, r14
0x18000e72b  call    WPP_SF_d
0x18000e730  jmp     loc_18000E859
0x18000e735  lea     rdx, [rsp+38h+Count]; Count
0x18000e73a  xor     ecx, ecx; Ids
0x18000e73c  xor     esi, esi
0x18000e73e  call    cs:__imp_NtQueryBootEntryOrder
0x18000e744  mov     ebx, eax
0x18000e746  test    eax, eax
0x18000e748  jns     loc_18000E7EB
0x18000e74e  cmp     eax, 0C0000023h
0x18000e753  jz      short loc_18000E77B
0x18000e755  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e75c  lea     rdi, WPP_GLOBAL_Control
0x18000e763  cmp     rcx, rdi
0x18000e766  jz      loc_18000E8A2
0x18000e76c  test    byte ptr [rcx+1Ch], 1
0x18000e770  jz      loc_18000E860
0x18000e776  lea     edx, [rsi+2Ah]
0x18000e779  jmp     short loc_18000E721
0x18000e77b  mov     ebx, [rsp+38h+Count]
0x18000e77f  shl     rbx, 2
0x18000e783  call    cs:__imp_GetProcessHeap
0x18000e789  mov     r8, rbx; dwBytes
0x18000e78c  mov     edx, 8; dwFlags
0x18000e791  mov     rcx, rax; hHeap
0x18000e794  call    cs:__imp_HeapAlloc
0x18000e79a  mov     rsi, rax
0x18000e79d  test    rax, rax
0x18000e7a0  jnz     short loc_18000E7DB
0x18000e7a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7a9  lea     rdi, WPP_GLOBAL_Control
0x18000e7b0  cmp     rcx, rdi
0x18000e7b3  jz      short loc_18000E7D1
0x18000e7b5  test    byte ptr [rcx+1Ch], 1
0x18000e7b9  jz      short loc_18000E7D1
0x18000e7bb  mov     rcx, [rcx+10h]
0x18000e7bf  lea     edx, [rax+2Bh]
0x18000e7c2  mov     r8, r14
0x18000e7c5  call    WPP_SF_
0x18000e7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7d1  mov     ebx, 0C0000017h
0x18000e7d6  jmp     loc_18000E860
0x18000e7db  lea     rdx, [rsp+38h+Count]; Count
0x18000e7e0  mov     rcx, rax; Ids
0x18000e7e3  call    cs:__imp_NtQueryBootEntryOrder
0x18000e7e9  mov     ebx, eax
0x18000e7eb  lea     rdi, WPP_GLOBAL_Control
0x18000e7f2  test    ebx, ebx
0x18000e7f4  jns     short loc_18000E81E
0x18000e7f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7fd  cmp     rcx, rdi
0x18000e800  jz      short loc_18000E840
0x18000e802  test    byte ptr [rcx+1Ch], 1
0x18000e806  jz      short loc_18000E840
0x18000e808  mov     edx, 2Ch ; ','
0x18000e80d  mov     r9d, ebx
0x18000e810  mov     rcx, [rcx+10h]
0x18000e814  mov     r8, r14
0x18000e817  call    WPP_SF_d
0x18000e81c  jmp     short loc_18000E839
0x18000e81e  mov     edx, [rsp+38h+Count]
0x18000e822  xor     ecx, ecx
0x18000e824  test    edx, edx
0x18000e826  jz      short loc_18000E837
0x18000e828  cmp     [rsi+rcx*4], ebp
0x18000e82b  jz      loc_18000E8B7
0x18000e831  inc     ecx
0x18000e833  cmp     ecx, edx
0x18000e835  jb      short loc_18000E828
0x18000e837  xor     ebx, ebx
0x18000e839  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e840  test    rsi, rsi
0x18000e843  jz      short loc_18000E860
0x18000e845  call    cs:__imp_GetProcessHeap
0x18000e84b  mov     r8, rsi; lpMem
0x18000e84e  xor     edx, edx; dwFlags
0x18000e850  mov     rcx, rax; hHeap
0x18000e853  call    cs:__imp_HeapFree
0x18000e859  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e860  cmp     rcx, rdi
0x18000e863  jz      short loc_18000E8A2
0x18000e865  test    byte ptr [rcx+1Ch], 4
0x18000e869  jz      short loc_18000E886
0x18000e86b  mov     rcx, [rcx+10h]
0x18000e86f  mov     edx, 2Eh ; '.'
0x18000e874  mov     r9d, ebx
0x18000e877  mov     r8, r14
0x18000e87a  call    WPP_SF_d
0x18000e87f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e886  cmp     rcx, rdi
0x18000e889  jz      short loc_18000E8A2
0x18000e88b  test    byte ptr [rcx+1Ch], 8
0x18000e88f  jz      short loc_18000E8A2
0x18000e891  mov     rcx, [rcx+10h]
0x18000e895  mov     edx, 2Fh ; '/'
0x18000e89a  mov     r8, r14
0x18000e89d  call    WPP_SF_
0x18000e8a2  mov     rbp, [rsp+38h+arg_10]
0x18000e8a7  mov     eax, ebx
0x18000e8a9  mov     rbx, [rsp+38h+arg_0]
0x18000e8ae  add     rsp, 20h
0x18000e8b2  pop     r14
0x18000e8b4  pop     rdi
0x18000e8b5  pop     rsi
0x18000e8b6  retn
0x18000e8b7  cmp     ecx, 0FFFFFFFFh
0x18000e8ba  jz      loc_18000E837
0x18000e8c0  dec     edx; Count
0x18000e8c2  cmp     ecx, edx
0x18000e8c4  jnb     short loc_18000E8D9
0x18000e8c6  lea     r8d, [rcx+1]
0x18000e8ca  mov     eax, [rsi+r8*4]
0x18000e8ce  mov     [rsi+rcx*4], eax
0x18000e8d1  mov     ecx, r8d
0x18000e8d4  cmp     r8d, edx
0x18000e8d7  jb      short loc_18000E8C6
0x18000e8d9  mov     rcx, rsi; Ids
0x18000e8dc  call    cs:__imp_NtSetBootEntryOrder
0x18000e8e2  mov     ebx, eax
0x18000e8e4  test    eax, eax
0x18000e8e6  jns     loc_18000E837
0x18000e8ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8f3  cmp     rcx, rdi
0x18000e8f6  jz      loc_18000E840
0x18000e8fc  test    byte ptr [rcx+1Ch], 1
0x18000e900  jz      loc_18000E840
0x18000e906  mov     edx, 2Dh ; '-'
0x18000e90b  mov     r9d, eax
0x18000e90e  jmp     loc_18000E810
```
