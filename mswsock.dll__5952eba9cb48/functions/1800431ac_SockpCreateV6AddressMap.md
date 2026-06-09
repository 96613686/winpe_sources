# SockpCreateV6AddressMap

- ea: `0x1800431ac`
- end: `0x180043456`
- name: `SockpCreateV6AddressMap`
- size: `682`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003eb24`

## callees

- `0x18003aec4`
- `0x1800431ac`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800431f0`
- `ntdll!RtlFreeHeap` at `0x1800432e2`
- `ntdll!RtlFreeHeap` at `0x180043306`
- `ntdll!RtlFreeHeap` at `0x18004338f`
- `ntdll!RtlFreeHeap` at `0x180043407`
- `ntdll!RtlFreeHeap` at `0x180043428`
- `ntdll!RtlFreeHeap` at `0x1800431f0`
- `ntdll!RtlFreeHeap` at `0x1800432e2`
- `ntdll!RtlFreeHeap` at `0x180043306`
- `ntdll!RtlFreeHeap` at `0x18004338f`
- `ntdll!RtlFreeHeap` at `0x180043407`
- `ntdll!RtlFreeHeap` at `0x180043428`
- `ntdll!NtDeviceIoControlFile` at `0x180043265`
- `ntdll!NtDeviceIoControlFile` at `0x180043265`

## pseudocode

```c
__int64 __fastcall SockpCreateV6AddressMap(_BYTE *a1)
{
  unsigned __int16 *v2; // rbx
  unsigned __int16 *OutputBuffer; // rax
  __int64 v4; // rcx
  unsigned int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rdi
  unsigned int v8; // esi
  __int64 v9; // rcx
  unsigned __int16 *v10; // rdx
  _QWORD *v12; // r10
  __int64 v13; // r9
  unsigned __int16 *v14; // r8
  __int64 v15; // rcx
  unsigned __int16 *v16; // rdx
  __int128 v17; // xmm0
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-38h] BYREF
  __int16 InputBuffer; // [rsp+98h] [rbp+10h] BYREF

  IoStatusBlock.Pointer = 0;
  InputBuffer = 23;
  IoStatusBlock.Information = (unsigned int)(30 * SockSanV6AddressCount + 244);
  v2 = 0;
  do
  {
    if ( v2 )
      RtlFreeHeap(SockPrivateHeap, 0, v2);
    OutputBuffer = (unsigned __int16 *)SockAllocateHeapRoutine(SockPrivateHeap, 0, LODWORD(IoStatusBlock.Information));
    v2 = OutputBuffer;
    if ( !OutputBuffer )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_l(v4, 85, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, LODWORD(IoStatusBlock.Information));
LABEL_30:
      v8 = 8;
      if ( !v2 )
      {
LABEL_32:
        if ( SockSanV6AddressMap )
        {
          RtlFreeHeap(SockPrivateHeap, 0, SockSanV6AddressMap);
          SockSanV6AddressMap = 0;
          SockSanV6AddressCount = 0;
        }
        return v8;
      }
LABEL_31:
      RtlFreeHeap(SockPrivateHeap, 0, v2);
      goto LABEL_32;
    }
    v5 = NtDeviceIoControlFile(
           SockSanHelperHandle,
           0,
           0,
           0,
           &IoStatusBlock,
           0x120B3u,
           &InputBuffer,
           2u,
           OutputBuffer,
           IoStatusBlock.Information);
  }
  while ( v5 == -2147483643 );
  if ( v5 )
  {
    if ( v5 != -1073741801 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_l(v6, 86, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, v5);
      v8 = 10107;
      goto LABEL_31;
    }
    goto LABEL_30;
  }
  v7 = *(unsigned int *)v2;
  v8 = 0;
  if ( (int)v7 <= 0 )
    goto LABEL_31;
  if ( (_DWORD)v7 == SockSanV6AddressCount )
  {
    v9 = 0;
    v10 = v2 + 2;
    while ( *((_QWORD *)SockSanV6AddressMap + 3 * v9 + 1) == *(_QWORD *)(v10 + 9)
         && *((_QWORD *)SockSanV6AddressMap + 3 * v9) == *(_QWORD *)(v10 + 5) )
    {
      v9 = (unsigned int)(v9 + 1);
      v10 = (unsigned __int16 *)((char *)v10 + *v10 + 4);
      if ( (unsigned int)v9 >= (unsigned int)v7 )
      {
        if ( (_DWORD)v9 != (_DWORD)v7 )
          break;
        RtlFreeHeap(SockPrivateHeap, 0, v2);
        *a1 = 0;
        return 0;
      }
    }
  }
  if ( SockSanV6AddressMap )
  {
    RtlFreeHeap(SockPrivateHeap, 0, SockSanV6AddressMap);
    SockSanV6AddressMap = 0;
  }
  SockSanV6AddressMap = (PVOID)SockAllocateHeapRoutine(SockPrivateHeap, 0, 24 * v7);
  v12 = SockSanV6AddressMap;
  if ( !SockSanV6AddressMap )
  {
    v8 = 8;
    goto LABEL_31;
  }
  v13 = 0;
  v14 = v2 + 2;
  do
  {
    v15 = 3 * v13;
    v16 = v14;
    v13 = (unsigned int)(v13 + 1);
    v14 = (unsigned __int16 *)((char *)v14 + *v14 + 4);
    v17 = *(_OWORD *)(v16 + 5);
    v12[v15 + 2] = 0;
    *(_OWORD *)&v12[v15] = v17;
  }
  while ( (unsigned int)v13 < (unsigned int)v7 );
  *a1 = 1;
  SockSanV6AddressCount = v7;
  RtlFreeHeap(SockPrivateHeap, 0, v2);
  return 0;
}

```

## disassembly

```asm
0x1800431ac  mov     r11, rsp
0x1800431af  push    rbx
0x1800431b0  push    rsi
0x1800431b1  push    rdi
0x1800431b2  push    r14
0x1800431b4  sub     rsp, 68h
0x1800431b8  mov     eax, 17h
0x1800431bd  mov     qword ptr [r11-38h], 0
0x1800431c5  mov     [r11+10h], ax
0x1800431ca  mov     r14, rcx
0x1800431cd  imul    eax, cs:SockSanV6AddressCount, 1Eh
0x1800431d4  add     eax, 0F4h
0x1800431d9  mov     [r11-30h], rax
0x1800431dd  xor     ebx, ebx
0x1800431df  test    rbx, rbx
0x1800431e2  jz      short loc_1800431FC
0x1800431e4  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800431eb  mov     r8, rbx; P
0x1800431ee  xor     edx, edx; Flags
0x1800431f0  call    cs:__imp_RtlFreeHeap
0x1800431f7  nop     dword ptr [rax+rax+00h]
0x1800431fc  mov     r8d, dword ptr [rsp+88h+var_38.Information]
0x180043201  xor     edx, edx
0x180043203  mov     rcx, cs:SockPrivateHeap
0x18004320a  mov     rax, cs:SockAllocateHeapRoutine
0x180043211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043216  mov     rbx, rax
0x180043219  test    rax, rax
0x18004321c  jz      loc_1800433D2
0x180043222  mov     eax, dword ptr [rsp+88h+var_38.Information]
0x180043226  xor     r9d, r9d; ApcContext
0x180043229  mov     rcx, cs:SockSanHelperHandle; FileHandle
0x180043230  xor     r8d, r8d; ApcRoutine
0x180043233  mov     [rsp+88h+OutputBufferLength], eax; OutputBufferLength
0x180043237  xor     edx, edx; Event
0x180043239  mov     [rsp+88h+OutputBuffer], rbx; OutputBuffer
0x18004323e  lea     rax, [rsp+88h+arg_8]
0x180043246  mov     [rsp+88h+InputBufferLength], 2; InputBufferLength
0x18004324e  mov     [rsp+88h+InputBuffer], rax; InputBuffer
0x180043253  lea     rax, [rsp+88h+var_38]
0x180043258  mov     [rsp+88h+IoControlCode], 120B3h; IoControlCode
0x180043260  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x180043265  call    cs:__imp_NtDeviceIoControlFile
0x18004326c  nop     dword ptr [rax+rax+00h]
0x180043271  cmp     eax, 80000005h
0x180043276  jz      loc_1800431DF
0x18004327c  test    eax, eax
0x18004327e  jnz     loc_1800433A7
0x180043284  mov     edi, [rbx]
0x180043286  xor     esi, esi
0x180043288  test    edi, edi
0x18004328a  jle     loc_1800433FB
0x180043290  cmp     edi, cs:SockSanV6AddressCount
0x180043296  mov     r8, cs:SockSanV6AddressMap; P
0x18004329d  jnz     short loc_1800432F8
0x18004329f  xor     ecx, ecx
0x1800432a1  lea     rdx, [rbx+4]
0x1800432a5  test    edi, edi
0x1800432a7  jz      short loc_1800432D2
0x1800432a9  mov     rax, [rdx+12h]
0x1800432ad  lea     r9, [rcx+rcx*2]
0x1800432b1  cmp     [r8+r9*8+8], rax
0x1800432b6  jnz     short loc_1800432F8
0x1800432b8  mov     rax, [rdx+0Ah]
0x1800432bc  cmp     [r8+r9*8], rax
0x1800432c0  jnz     short loc_1800432F8
0x1800432c2  movzx   eax, word ptr [rdx]
0x1800432c5  inc     ecx
0x1800432c7  add     rdx, 4
0x1800432cb  add     rdx, rax
0x1800432ce  cmp     ecx, edi
0x1800432d0  jb      short loc_1800432A9
0x1800432d2  cmp     ecx, edi
0x1800432d4  jnz     short loc_1800432F8
0x1800432d6  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800432dd  mov     r8, rbx; P
0x1800432e0  xor     edx, edx; Flags
0x1800432e2  call    cs:__imp_RtlFreeHeap
0x1800432e9  nop     dword ptr [rax+rax+00h]
0x1800432ee  mov     [r14], sil
0x1800432f1  xor     eax, eax
0x1800432f3  jmp     loc_18004344B
0x1800432f8  test    r8, r8
0x1800432fb  jz      short loc_180043319
0x1800432fd  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180043304  xor     edx, edx; Flags
0x180043306  call    cs:__imp_RtlFreeHeap
0x18004330d  nop     dword ptr [rax+rax+00h]
0x180043312  mov     cs:SockSanV6AddressMap, rsi
0x180043319  mov     rcx, cs:SockPrivateHeap
0x180043320  lea     r8, [rdi+rdi*2]
0x180043324  mov     rax, cs:SockAllocateHeapRoutine
0x18004332b  xor     edx, edx
0x18004332d  shl     r8, 3
0x180043331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043336  mov     cs:SockSanV6AddressMap, rax
0x18004333d  mov     r10, rax
0x180043340  test    rax, rax
0x180043343  jz      short loc_1800433A0
0x180043345  xor     r9d, r9d
0x180043348  lea     r8, [rbx+4]
0x18004334c  test    edi, edi
0x18004334e  jz      short loc_18004337D
0x180043350  movzx   eax, word ptr [r8]
0x180043354  lea     rcx, [r9+r9*2]
0x180043358  mov     rdx, r8
0x18004335b  inc     r9d
0x18004335e  add     r8, 4
0x180043362  add     r8, rax
0x180043365  movups  xmm0, xmmword ptr [rdx+0Ah]
0x180043369  mov     [r10+rcx*8+10h], rsi
0x18004336e  movdqu  xmmword ptr [r10+rcx*8], xmm0
0x180043374  cmp     r9d, edi
0x180043377  jb      short loc_180043350
0x180043379  mov     byte ptr [r14], 1
0x18004337d  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180043384  mov     r8, rbx; P
0x180043387  xor     edx, edx; Flags
0x180043389  mov     cs:SockSanV6AddressCount, edi
0x18004338f  call    cs:__imp_RtlFreeHeap
0x180043396  nop     dword ptr [rax+rax+00h]
0x18004339b  jmp     loc_1800432F1
0x1800433a0  mov     esi, 8
0x1800433a5  jmp     short loc_1800433FB
0x1800433a7  cmp     eax, 0C0000017h
0x1800433ac  jz      short loc_1800433F1
0x1800433ae  test    byte ptr cs:xmmword_180063D60, 2
0x1800433b5  jz      short loc_1800433CB
0x1800433b7  mov     edx, 56h ; 'V'
0x1800433bc  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x1800433c3  mov     r9d, eax
0x1800433c6  call    WPP_SF_l
0x1800433cb  mov     esi, 277Bh
0x1800433d0  jmp     short loc_1800433FB
0x1800433d2  test    byte ptr cs:xmmword_180063D60, 2
0x1800433d9  jz      short loc_1800433F1
0x1800433db  mov     r9d, dword ptr [rsp+88h+var_38.Information]
0x1800433e0  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x1800433e7  mov     edx, 55h ; 'U'
0x1800433ec  call    WPP_SF_l
0x1800433f1  mov     esi, 8
0x1800433f6  test    rbx, rbx
0x1800433f9  jz      short loc_180043413
0x1800433fb  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180043402  mov     r8, rbx; P
0x180043405  xor     edx, edx; Flags
0x180043407  call    cs:__imp_RtlFreeHeap
0x18004340e  nop     dword ptr [rax+rax+00h]
0x180043413  mov     r8, cs:SockSanV6AddressMap; P
0x18004341a  test    r8, r8
0x18004341d  jz      short loc_180043449
0x18004341f  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180043426  xor     edx, edx; Flags
0x180043428  call    cs:__imp_RtlFreeHeap
0x18004342f  nop     dword ptr [rax+rax+00h]
0x180043434  mov     cs:SockSanV6AddressMap, 0
0x18004343f  mov     cs:SockSanV6AddressCount, 0
0x180043449  mov     eax, esi
0x18004344b  add     rsp, 68h
0x18004344f  pop     r14
0x180043451  pop     rdi
0x180043452  pop     rsi
0x180043453  pop     rbx
0x180043454  retn
```
