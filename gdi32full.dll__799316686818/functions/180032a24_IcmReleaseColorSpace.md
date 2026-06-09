# IcmReleaseColorSpace

- ea: `0x180032a24`
- end: `0x180032b9a`
- name: `IcmReleaseColorSpace`
- size: `374`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x18001ec70`
- `0x18001f310`
- `0x180025760`
- `0x1800267d0`
- `0x180032130`
- `0x180032768`
- `0x180032848`
- `0x180032ba0`
- `0x18003e184`
- `0x18006a7c4`
- `0x18006b93c`
- `0x180072b80`
- `0x180087f90`
- `0x1800891e4`
- `0x18008fa90`
- `0x180091520`

## callees

- `0x180032a24`
- `0x180034c50`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180032b88`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180032b88`
- `ntdll!RtlFreeHeap` at `0x180032aa1`
- `ntdll!RtlFreeHeap` at `0x180032ac7`
- `ntdll!RtlFreeHeap` at `0x180032b1b`
- `ntdll!RtlFreeHeap` at `0x180032b6e`
- `ntdll!RtlFreeHeap` at `0x180032aa1`
- `ntdll!RtlFreeHeap` at `0x180032ac7`
- `ntdll!RtlFreeHeap` at `0x180032b1b`
- `ntdll!RtlFreeHeap` at `0x180032b6e`
- `ntdll!RtlEnterCriticalSection` at `0x180032a4c`
- `ntdll!RtlEnterCriticalSection` at `0x180032a4c`
- `ntdll!RtlLeaveCriticalSection` at `0x180032b28`
- `ntdll!RtlLeaveCriticalSection` at `0x180032b28`

## pseudocode

```c
void __fastcall IcmReleaseColorSpace(__int64 a1, __int64 *a2, int a3)
{
  int v6; // eax
  void *v7; // r8
  void *v8; // r8
  __int64 *v9; // rax
  __int64 **v10; // rdx

  if ( a2 )
  {
    RtlEnterCriticalSection(&semColorSpaceCache);
    v6 = --*((_DWORD *)a2 + 7);
    if ( ((a2[3] & 0x10000) == 0 || !v6) && (!v6 || a3 && a2[2] == a1) )
    {
      if ( a2[4] )
        IcmUnrealizeColorProfile(a2);
      if ( (a2[3] & 0x40000) != 0 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)a2[7]);
        a2[7] = 0;
      }
      v7 = (void *)a2[9];
      if ( v7 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
        a2[9] = 0;
      }
      v8 = (void *)a2[10];
      if ( v8 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
        a2[10] = 0;
      }
      if ( (a2[3] & 0x80000) != 0 )
        DeleteFileW((LPCWSTR)a2 + 78);
      v9 = (__int64 *)*a2;
      if ( *(__int64 **)(*a2 + 8) != a2 || (v10 = (__int64 **)a2[1], *v10 != a2) )
        __fastfail(3u);
      --cCachedColorSpace;
      *v10 = v9;
      v9[1] = (__int64)v10;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a2);
    }
    RtlLeaveCriticalSection(&semColorSpaceCache);
  }
}

```

## disassembly

```asm
0x180032a24  test    rdx, rdx
0x180032a27  jz      locret_180032B3D
0x180032a2d  mov     [rsp+arg_0], rbx
0x180032a32  mov     [rsp+arg_8], rsi
0x180032a37  push    rdi
0x180032a38  sub     rsp, 20h
0x180032a3c  mov     rdi, rcx
0x180032a3f  mov     esi, r8d
0x180032a42  lea     rcx, semColorSpaceCache; CriticalSection
0x180032a49  mov     rbx, rdx
0x180032a4c  call    cs:__imp_RtlEnterCriticalSection
0x180032a52  dec     dword ptr [rbx+1Ch]
0x180032a55  test    dword ptr [rbx+18h], 10000h
0x180032a5c  mov     eax, [rbx+1Ch]
0x180032a5f  jz      short loc_180032A69
0x180032a61  test    eax, eax
0x180032a63  jnz     loc_180032B21
0x180032a69  test    eax, eax
0x180032a6b  jnz     loc_180032B3E
0x180032a71  cmp     qword ptr [rbx+20h], 0
0x180032a76  jnz     loc_180032B4E
0x180032a7c  test    dword ptr [rbx+18h], 40000h
0x180032a83  jnz     loc_180032B5B
0x180032a89  mov     r8, [rbx+48h]; P
0x180032a8d  test    r8, r8
0x180032a90  jz      short loc_180032AAF
0x180032a92  mov     rcx, gs:60h
0x180032a9b  xor     edx, edx; Flags
0x180032a9d  mov     rcx, [rcx+30h]; HeapHandle
0x180032aa1  call    cs:__imp_RtlFreeHeap
0x180032aa7  mov     qword ptr [rbx+48h], 0
0x180032aaf  mov     r8, [rbx+50h]; P
0x180032ab3  test    r8, r8
0x180032ab6  jz      short loc_180032AD5
0x180032ab8  mov     rcx, gs:60h
0x180032ac1  xor     edx, edx; Flags
0x180032ac3  mov     rcx, [rcx+30h]; HeapHandle
0x180032ac7  call    cs:__imp_RtlFreeHeap
0x180032acd  mov     qword ptr [rbx+50h], 0
0x180032ad5  test    dword ptr [rbx+18h], 80000h
0x180032adc  jnz     loc_180032B81
0x180032ae2  mov     rax, [rbx]
0x180032ae5  cmp     [rax+8], rbx
0x180032ae9  jnz     loc_180032B93
0x180032aef  mov     rdx, [rbx+8]
0x180032af3  cmp     [rdx], rbx
0x180032af6  jnz     loc_180032B93
0x180032afc  dec     cs:?cCachedColorSpace@@3KA; ulong cCachedColorSpace
0x180032b02  mov     r8, rbx; P
0x180032b05  mov     [rdx], rax
0x180032b08  mov     [rax+8], rdx
0x180032b0c  xor     edx, edx; Flags
0x180032b0e  mov     rcx, gs:60h
0x180032b17  mov     rcx, [rcx+30h]; HeapHandle
0x180032b1b  call    cs:__imp_RtlFreeHeap
0x180032b21  lea     rcx, semColorSpaceCache; CriticalSection
0x180032b28  call    cs:__imp_RtlLeaveCriticalSection
0x180032b2e  mov     rbx, [rsp+28h+arg_0]
0x180032b33  mov     rsi, [rsp+28h+arg_8]
0x180032b38  add     rsp, 20h
0x180032b3c  pop     rdi
0x180032b3d  retn
0x180032b3e  test    esi, esi
0x180032b40  jz      short loc_180032B21
0x180032b42  cmp     [rbx+10h], rdi
0x180032b46  jz      loc_180032A71
0x180032b4c  jmp     short loc_180032B21
0x180032b4e  mov     rcx, rbx
0x180032b51  call    IcmUnrealizeColorProfile
0x180032b56  jmp     loc_180032A7C
0x180032b5b  mov     rcx, gs:60h
0x180032b64  xor     edx, edx; Flags
0x180032b66  mov     r8, [rbx+38h]; P
0x180032b6a  mov     rcx, [rcx+30h]; HeapHandle
0x180032b6e  call    cs:__imp_RtlFreeHeap
0x180032b74  mov     qword ptr [rbx+38h], 0
0x180032b7c  jmp     loc_180032A89
0x180032b81  lea     rcx, [rbx+9Ch]; lpFileName
0x180032b88  call    cs:__imp_DeleteFileW
0x180032b8e  jmp     loc_180032AE2
0x180032b93  mov     ecx, 3
0x180032b98  int     29h; Win8: RtlFailFast(ecx)
```
