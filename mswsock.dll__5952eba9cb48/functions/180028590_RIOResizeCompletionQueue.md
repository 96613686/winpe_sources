# RIOResizeCompletionQueue

- ea: `0x180028590`
- end: `0x18002877e`
- name: `RIOResizeCompletionQueue`
- size: `494`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800222f0`
- `0x180022bd2`
- `0x18002819c`
- `0x180028590`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800286ed`
- `ntdll!RtlFreeHeap` at `0x1800286ed`
- `ntdll!NtDeviceIoControlFile` at `0x1800286d1`
- `ntdll!NtDeviceIoControlFile` at `0x1800286d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002872f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002874a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002872f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002874a`

## pseudocode

```c
__int64 __fastcall RIOResizeCompletionQueue(__int128 *a1, int a2)
{
  __int128 v3; // xmm6
  void *v4; // rdi
  __int64 v5; // rsi
  __int64 HeapRoutine; // rax
  HANDLE RegDomain; // rax
  NTSTATUS v8; // eax
  DWORD v10; // ecx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-58h] BYREF
  __int128 InputBuffer; // [rsp+60h] [rbp-48h] BYREF
  __int64 v13; // [rsp+70h] [rbp-38h]

  v13 = 0;
  IoStatusBlock = 0;
  InputBuffer = 0;
  if ( !a1 || (unsigned int)(a2 - 1) > 0x7FFFFFF )
  {
    SetLastError(0x2726u);
    return 0;
  }
  v3 = *a1;
  v4 = (void *)*((_QWORD *)a1 + 2);
  v5 = (unsigned int)(a2 + 1);
  HeapRoutine = SockAllocateHeapRoutine(SockPrivateHeap, 0, 24 * v5 + 16);
  *((_QWORD *)a1 + 2) = HeapRoutine;
  if ( !HeapRoutine )
  {
LABEL_14:
    v10 = 10055;
    goto LABEL_15;
  }
  *(_DWORD *)a1 = -1582119980;
  *((_DWORD *)a1 + 1) = v5;
  *(_BYTE *)(HeapRoutine + 8) = 0;
  **((_DWORD **)a1 + 2) = 0;
  *(_DWORD *)(*((_QWORD *)a1 + 2) + 4LL) = 0;
  memset_0((void *)(*((_QWORD *)a1 + 2) + 16LL), 0, 24 * v5);
  DWORD1(InputBuffer) = *((_DWORD *)a1 + 2);
  LODWORD(InputBuffer) = 8;
  HIDWORD(InputBuffer) = 24 * v5 + 16;
  v13 = *((_QWORD *)a1 + 2);
  RegDomain = MswRioRegDomain;
  DWORD2(InputBuffer) = v5;
  if ( MswRioRegDomain == (HANDLE)-1LL )
    RegDomain = CreateRegDomain();
  v8 = NtDeviceIoControlFile(RegDomain, 0, 0, 0, &IoStatusBlock, 0x1211Bu, &InputBuffer, 0x18u, 0, 0);
  if ( !v8 )
  {
    RtlFreeHeap(SockPrivateHeap, 0, v4);
    return 1;
  }
  if ( v8 != -1073741618 )
  {
    if ( v8 != -1073741801 )
    {
      if ( v8 == -1073741811 )
        v10 = 10022;
      else
        v10 = 10014;
      goto LABEL_15;
    }
    goto LABEL_14;
  }
  v10 = 10059;
LABEL_15:
  SetLastError(v10);
  *a1 = v3;
  *((_QWORD *)a1 + 2) = v4;
  return 0;
}

```

## disassembly

```asm
0x180028590  mov     rax, rsp
0x180028593  mov     [rax+18h], rbx
0x180028597  push    rbp
0x180028598  push    rsi
0x180028599  push    rdi
0x18002859a  sub     rsp, 90h
0x1800285a1  movaps  xmmword ptr [rax-28h], xmm6
0x1800285a5  mov     rax, cs:__security_cookie
0x1800285ac  xor     rax, rsp
0x1800285af  mov     [rsp+0A8h+var_30], rax
0x1800285b4  xor     eax, eax
0x1800285b6  xorps   xmm0, xmm0
0x1800285b9  mov     [rsp+0A8h+var_38], rax
0x1800285be  xorps   xmm1, xmm1
0x1800285c1  mov     rbx, rcx
0x1800285c4  movups  xmmword ptr [rsp+0A8h+var_58], xmm0
0x1800285c9  movups  [rsp+0A8h+var_48], xmm1
0x1800285ce  test    rcx, rcx
0x1800285d1  jz      loc_180028745
0x1800285d7  lea     eax, [rdx-1]
0x1800285da  cmp     eax, 7FFFFFFh
0x1800285df  ja      loc_180028745
0x1800285e5  movups  xmm6, xmmword ptr [rcx]
0x1800285e8  mov     rdi, [rcx+10h]
0x1800285ec  lea     esi, [rdx+1]
0x1800285ef  mov     rax, cs:SockAllocateHeapRoutine
0x1800285f6  lea     rcx, [rsi+rsi*2]
0x1800285fa  lea     rbp, ds:0[rcx*8]
0x180028602  xor     edx, edx
0x180028604  mov     rcx, cs:SockPrivateHeap
0x18002860b  lea     r8, [rbp+10h]
0x18002860f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028614  mov     [rbx+10h], rax
0x180028618  test    rax, rax
0x18002861b  jz      loc_18002872A
0x180028621  mov     dword ptr [rbx], 0A1B2C3D4h
0x180028627  mov     r8, rbp; Size
0x18002862a  mov     [rbx+4], esi
0x18002862d  xor     edx, edx; Val
0x18002862f  mov     byte ptr [rax+8], 0
0x180028633  mov     rax, [rbx+10h]
0x180028637  mov     dword ptr [rax], 0
0x18002863d  mov     rax, [rbx+10h]
0x180028641  mov     dword ptr [rax+4], 0
0x180028648  mov     rcx, [rbx+10h]
0x18002864c  add     rcx, 10h; void *
0x180028650  call    memset_0
0x180028655  mov     eax, [rbx+8]
0x180028658  mov     dword ptr [rsp+0A8h+var_48+4], eax
0x18002865c  lea     eax, [rsi+rsi*2]
0x18002865f  lea     eax, ds:10h[rax*8]
0x180028666  mov     dword ptr [rsp+0A8h+var_48], 8
0x18002866e  mov     dword ptr [rsp+0A8h+var_48+0Ch], eax
0x180028672  mov     rax, [rbx+10h]
0x180028676  mov     [rsp+0A8h+var_38], rax
0x18002867b  mov     rax, cs:MswRioRegDomain
0x180028682  mov     dword ptr [rsp+0A8h+var_48+8], esi
0x180028686  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002868a  jnz     short loc_180028691
0x18002868c  call    CreateRegDomain
0x180028691  mov     [rsp+0A8h+OutputBufferLength], 0; OutputBufferLength
0x180028699  lea     rcx, [rsp+0A8h+var_48]
0x18002869e  mov     [rsp+0A8h+OutputBuffer], 0; OutputBuffer
0x1800286a7  xor     r9d, r9d; ApcContext
0x1800286aa  mov     [rsp+0A8h+InputBufferLength], 18h; InputBufferLength
0x1800286b2  xor     r8d, r8d; ApcRoutine
0x1800286b5  mov     [rsp+0A8h+InputBuffer], rcx; InputBuffer
0x1800286ba  xor     edx, edx; Event
0x1800286bc  lea     rcx, [rsp+0A8h+var_58]
0x1800286c1  mov     [rsp+0A8h+IoControlCode], 1211Bh; IoControlCode
0x1800286c9  mov     [rsp+0A8h+IoStatusBlock], rcx; IoStatusBlock
0x1800286ce  mov     rcx, rax; FileHandle
0x1800286d1  call    cs:__imp_NtDeviceIoControlFile
0x1800286d8  nop     dword ptr [rax+rax+00h]
0x1800286dd  test    eax, eax
0x1800286df  jnz     short loc_180028700
0x1800286e1  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800286e8  mov     r8, rdi; P
0x1800286eb  xor     edx, edx; Flags
0x1800286ed  call    cs:__imp_RtlFreeHeap
0x1800286f4  nop     dword ptr [rax+rax+00h]
0x1800286f9  mov     eax, 1
0x1800286fe  jmp     short loc_180028758
0x180028700  cmp     eax, 0C00000CEh
0x180028705  jnz     short loc_18002870E
0x180028707  mov     ecx, 274Bh
0x18002870c  jmp     short loc_18002872F
0x18002870e  cmp     eax, 0C0000017h
0x180028713  jz      short loc_18002872A
0x180028715  cmp     eax, 0C000000Dh
0x18002871a  jnz     short loc_180028723
0x18002871c  mov     ecx, 2726h
0x180028721  jmp     short loc_18002872F
0x180028723  mov     ecx, 271Eh
0x180028728  jmp     short loc_18002872F
0x18002872a  mov     ecx, 2747h; dwErrCode
0x18002872f  call    cs:__imp_SetLastError
0x180028736  nop     dword ptr [rax+rax+00h]
0x18002873b  movdqu  xmmword ptr [rbx], xmm6
0x18002873f  mov     [rbx+10h], rdi
0x180028743  jmp     short loc_180028756
0x180028745  mov     ecx, 2726h; dwErrCode
0x18002874a  call    cs:__imp_SetLastError
0x180028751  nop     dword ptr [rax+rax+00h]
0x180028756  xor     eax, eax
0x180028758  mov     rcx, [rsp+0A8h+var_30]
0x18002875d  xor     rcx, rsp; StackCookie
0x180028760  call    __security_check_cookie
0x180028765  lea     r11, [rsp+0A8h+var_18]
0x18002876d  mov     rbx, [r11+30h]
0x180028771  movaps  xmm6, xmmword ptr [r11-10h]
0x180028776  mov     rsp, r11
0x180028779  pop     rdi
0x18002877a  pop     rsi
0x18002877b  pop     rbp
0x18002877c  retn
```
