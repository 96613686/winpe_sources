# FltpLinkFilterIntoFrame

- ea: `0x180055fd0`
- end: `0x1800560a8`
- name: `FltpLinkFilterIntoFrame`
- size: `216`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004c810`

## callees

- `0x180055fd0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180055fe7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180055fe7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005608c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18005608c`
- `ntoskrnl!ExReleaseFastResource` at `0x180056080`
- `ntoskrnl!ExReleaseFastResource` at `0x180056080`
- `ntoskrnl!RtlCompareAltitudes` at `0x180056026`
- `ntoskrnl!RtlCompareAltitudes` at `0x180056026`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x180055ffc`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x180055ffc`

## pseudocode

```c
__int64 __fastcall FltpLinkFilterIntoFrame(__int64 a1)
{
  __int64 v1; // rbp
  LONG v3; // edi
  __int64 v4; // r8
  const UNICODE_STRING *v5; // rbx
  unsigned int v6; // ebx
  __int64 *Buffer; // rcx
  __int64 v8; // rdx

  v1 = *(_QWORD *)(a1 + 56);
  v3 = -1;
  KeEnterCriticalRegion();
  LOBYTE(v4) = 1;
  ExAcquireFastResourceExclusive(v1 + 72, 0, v4);
  v5 = *(const UNICODE_STRING **)(v1 + 176);
  if ( v5 == (const UNICODE_STRING *)(v1 + 176) )
    goto LABEL_7;
  do
  {
    if ( (*(_DWORD *)&v5[-1].Length & 2) == 0 )
    {
      v3 = RtlCompareAltitudes(v5 + 4, (PCUNICODE_STRING)(a1 + 80));
      if ( v3 <= 0 )
        break;
    }
    v5 = *(const UNICODE_STRING **)&v5->Length;
  }
  while ( v5 != (const UNICODE_STRING *)(v1 + 176) );
  if ( v3 )
  {
LABEL_7:
    Buffer = (__int64 *)v5->Buffer;
    v8 = *Buffer;
    if ( *(__int64 **)(*Buffer + 8) != Buffer )
      __fastfail(3u);
    *(_QWORD *)(a1 + 16) = v8;
    *(_QWORD *)(a1 + 24) = Buffer;
    *(_QWORD *)(v8 + 8) = a1 + 16;
    *Buffer = a1 + 16;
    _InterlockedIncrement((volatile signed __int32 *)(v1 + 192));
    v6 = 0;
  }
  else
  {
    v6 = -1071906799;
  }
  ExReleaseFastResource(v1 + 72, 0);
  KeLeaveCriticalRegion();
  return v6;
}

```

## disassembly

```asm
0x180055fd0  push    rbx
0x180055fd2  push    rbp
0x180055fd3  push    rsi
0x180055fd4  push    rdi
0x180055fd5  push    r14
0x180055fd7  push    r15
0x180055fd9  sub     rsp, 28h
0x180055fdd  mov     rbp, [rcx+38h]
0x180055fe1  mov     r14, rcx
0x180055fe4  or      edi, 0FFFFFFFFh
0x180055fe7  call    cs:__imp_KeEnterCriticalRegion
0x180055fee  nop     dword ptr [rax+rax+00h]
0x180055ff3  mov     r8b, 1
0x180055ff6  lea     rcx, [rbp+48h]
0x180055ffa  xor     edx, edx
0x180055ffc  call    cs:__imp_ExAcquireFastResourceExclusive
0x180056003  nop     dword ptr [rax+rax+00h]
0x180056008  lea     rsi, [rbp+0B0h]
0x18005600f  mov     rbx, [rsi]
0x180056012  cmp     rbx, rsi
0x180056015  jz      short loc_18005604B
0x180056017  mov     eax, [rbx-10h]
0x18005601a  test    al, 2
0x18005601c  jnz     short loc_180056038
0x18005601e  lea     rdx, [r14+50h]; Altitude2
0x180056022  lea     rcx, [rbx+40h]; Altitude1
0x180056026  call    cs:__imp_RtlCompareAltitudes
0x18005602d  nop     dword ptr [rax+rax+00h]
0x180056032  mov     edi, eax
0x180056034  test    eax, eax
0x180056036  jle     short loc_180056040
0x180056038  mov     rbx, [rbx]
0x18005603b  cmp     rbx, rsi
0x18005603e  jnz     short loc_180056017
0x180056040  test    edi, edi
0x180056042  jnz     short loc_18005604B
0x180056044  mov     ebx, 0C01C0011h
0x180056049  jmp     short loc_18005607A
0x18005604b  mov     rcx, [rbx+8]
0x18005604f  mov     rdx, [rcx]
0x180056052  cmp     [rdx+8], rcx
0x180056056  jz      short loc_18005605F
0x180056058  mov     ecx, 3
0x18005605d  int     29h; Win8: RtlFailFast(ecx)
0x18005605f  lea     rax, [r14+10h]
0x180056063  mov     [rax], rdx
0x180056066  mov     [rax+8], rcx
0x18005606a  mov     [rdx+8], rax
0x18005606e  mov     [rcx], rax
0x180056071  lock inc dword ptr [rbp+0C0h]
0x180056078  xor     ebx, ebx
0x18005607a  xor     edx, edx
0x18005607c  lea     rcx, [rbp+48h]
0x180056080  call    cs:__imp_ExReleaseFastResource
0x180056087  nop     dword ptr [rax+rax+00h]
0x18005608c  call    cs:__imp_KeLeaveCriticalRegion
0x180056093  nop     dword ptr [rax+rax+00h]
0x180056098  mov     eax, ebx
0x18005609a  add     rsp, 28h
0x18005609e  pop     r15
0x1800560a0  pop     r14
0x1800560a2  pop     rdi
0x1800560a3  pop     rsi
0x1800560a4  pop     rbp
0x1800560a5  pop     rbx
0x1800560a6  retn
```
