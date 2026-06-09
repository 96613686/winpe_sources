# FatTunnelFcbOrDcb

- ea: `0x140033e84`
- end: `0x14003404e`
- name: `FatTunnelFcbOrDcb`
- size: `458`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140024bd4`
- `0x14003bea4`

## callees

- `0x14000c230`
- `0x140033e84`

## import_xrefs

- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140033f78`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140033fcb`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140033f78`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x140033fcb`
- `ntoskrnl!RtlOemStringToCountedUnicodeString` at `0x140033f0a`
- `ntoskrnl!RtlOemStringToCountedUnicodeString` at `0x140033f0a`
- `ntoskrnl!FsRtlDeleteKeyFromTunnelCache` at `0x140033edc`
- `ntoskrnl!FsRtlDeleteKeyFromTunnelCache` at `0x140033edc`
- `ntoskrnl!FsRtlAddToTunnelCache` at `0x140034029`
- `ntoskrnl!FsRtlAddToTunnelCache` at `0x140034029`

## pseudocode

```c
void __fastcall FatTunnelFcbOrDcb(__int64 a1, __int64 a2)
{
  int v4; // r9d
  USHORT Length; // cx
  unsigned __int16 v6; // di
  PWSTR Buffer; // r8
  __int64 v8; // rdx
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp+7h] BYREF
  char v11; // [rsp+60h] [rbp+17h] BYREF

  *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
  SourceString = 0;
  if ( *(_WORD *)a1 == 1283 )
  {
    FsRtlDeleteKeyFromTunnelCache(
      (TUNNEL *)(*(_QWORD *)(a1 + 184) + 1032LL),
      *(_QWORD *)(a1 + 256) ^ *(unsigned int *)(a1 + 128));
  }
  else
  {
    *(_DWORD *)&DestinationString.Length = 1572864;
    DestinationString.Buffer = (PWSTR)&v11;
    RtlOemStringToCountedUnicodeString(&DestinationString, (PCOEM_STRING)(a1 + 480), 0);
    v4 = *(_DWORD *)(a1 + 192);
    if ( (v4 & 0x3000) != 0 )
    {
      Length = DestinationString.Length;
      v6 = 0;
      Buffer = DestinationString.Buffer;
      if ( DestinationString.Length >> 1 )
      {
        do
        {
          if ( DestinationString.Buffer[v6] == 46 )
            break;
          ++v6;
        }
        while ( v6 < (unsigned __int16)(DestinationString.Length >> 1) );
      }
      if ( (v4 & 0x1000) != 0 )
      {
        SourceString.Buffer = DestinationString.Buffer;
        SourceString.Length = 2 * v6;
        SourceString.MaximumLength = 2 * v6;
        RtlDowncaseUnicodeString(&SourceString, &SourceString, 0);
        Buffer = DestinationString.Buffer;
        Length = DestinationString.Length;
      }
      if ( (*(_DWORD *)(a1 + 192) & 0x2000) != 0 )
      {
        v8 = (unsigned __int16)(v6 + 1);
        if ( 2 * v8 < (unsigned __int64)Length )
        {
          SourceString.Buffer = &Buffer[v8];
          SourceString.Length = Length - 2 * v8;
          SourceString.MaximumLength = SourceString.Length;
          RtlDowncaseUnicodeString(&SourceString, &SourceString, 0);
        }
      }
    }
    FsRtlAddToTunnelCache(
      (TUNNEL *)(*(_QWORD *)(a1 + 184) + 1032LL),
      *(_QWORD *)(*(_QWORD *)(a1 + 176) + 256LL) ^ *(unsigned int *)(*(_QWORD *)(a1 + 176) + 128LL),
      &DestinationString,
      (UNICODE_STRING *)(a1 + 552),
      (*(_DWORD *)(a2 + 4) & 0x800) != 0,
      8u,
      (void *)(a1 + 256));
  }
}

```

## disassembly

```asm
0x140033e84  push    rbp
0x140033e86  push    rbx
0x140033e87  push    rsi
0x140033e88  push    rdi
0x140033e89  lea     rbp, [rsp-3Fh]
0x140033e8e  sub     rsp, 88h
0x140033e95  mov     rax, cs:__security_cookie
0x140033e9c  xor     rax, rsp
0x140033e9f  mov     [rbp+57h+var_28], rax
0x140033ea3  mov     eax, 503h
0x140033ea8  mov     dword ptr [rbp+57h+DestinationString+4], 0
0x140033eaf  xorps   xmm0, xmm0
0x140033eb2  mov     rsi, rdx
0x140033eb5  mov     rbx, rcx
0x140033eb8  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x140033ebc  cmp     [rcx], ax
0x140033ebf  jnz     short loc_140033EED
0x140033ec1  mov     edx, [rcx+80h]
0x140033ec7  xor     rdx, [rcx+100h]; DirectoryKey
0x140033ece  mov     rcx, [rcx+0B8h]
0x140033ed5  add     rcx, 408h; Cache
0x140033edc  call    cs:__imp_FsRtlDeleteKeyFromTunnelCache
0x140033ee3  nop     dword ptr [rax+rax+00h]
0x140033ee8  jmp     loc_140034035
0x140033eed  lea     rax, [rbp+57h+var_40]
0x140033ef1  mov     dword ptr [rbp+57h+DestinationString.Length], 180000h
0x140033ef8  lea     rdx, [rcx+1E0h]; SourceString
0x140033eff  mov     [rbp+57h+DestinationString.Buffer], rax
0x140033f03  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140033f07  xor     r8d, r8d; AllocateDestinationString
0x140033f0a  call    cs:__imp_RtlOemStringToCountedUnicodeString
0x140033f11  nop     dword ptr [rax+rax+00h]
0x140033f16  mov     r9d, [rbx+0C0h]
0x140033f1d  test    r9d, 3000h
0x140033f24  jz      loc_140033FD7
0x140033f2a  movzx   ecx, [rbp+57h+DestinationString.Length]
0x140033f2e  xor     edi, edi
0x140033f30  mov     r8, [rbp+57h+DestinationString.Buffer]
0x140033f34  movzx   edx, cx
0x140033f37  shr     dx, 1
0x140033f3a  xor     eax, eax
0x140033f3c  cmp     ax, dx
0x140033f3f  jnb     short loc_140033F54
0x140033f41  movzx   eax, di
0x140033f44  cmp     word ptr [r8+rax*2], 2Eh ; '.'
0x140033f4a  jz      short loc_140033F54
0x140033f4c  inc     di
0x140033f4f  cmp     di, dx
0x140033f52  jb      short loc_140033F41
0x140033f54  bt      r9d, 0Ch
0x140033f59  jnb     short loc_140033F8C
0x140033f5b  movzx   eax, di
0x140033f5e  mov     [rbp+57h+SourceString.Buffer], r8
0x140033f62  add     ax, ax
0x140033f65  lea     rdx, [rbp+57h+SourceString]; SourceString
0x140033f69  xor     r8d, r8d; AllocateDestinationString
0x140033f6c  mov     [rbp+57h+SourceString.Length], ax
0x140033f70  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x140033f74  mov     [rbp+57h+SourceString.MaximumLength], ax
0x140033f78  call    cs:__imp_RtlDowncaseUnicodeString
0x140033f7f  nop     dword ptr [rax+rax+00h]
0x140033f84  mov     r8, [rbp+57h+DestinationString.Buffer]
0x140033f88  movzx   ecx, [rbp+57h+DestinationString.Length]
0x140033f8c  test    dword ptr [rbx+0C0h], 2000h
0x140033f96  jz      short loc_140033FD7
0x140033f98  inc     di
0x140033f9b  movzx   eax, cx
0x140033f9e  movzx   edx, di
0x140033fa1  lea     r9, [rdx+rdx]
0x140033fa5  cmp     r9, rax
0x140033fa8  jnb     short loc_140033FD7
0x140033faa  add     dx, dx
0x140033fad  lea     rax, [r9+r8]
0x140033fb1  sub     cx, dx
0x140033fb4  mov     [rbp+57h+SourceString.Buffer], rax
0x140033fb8  mov     [rbp+57h+SourceString.Length], cx
0x140033fbc  lea     rdx, [rbp+57h+SourceString]; SourceString
0x140033fc0  mov     [rbp+57h+SourceString.MaximumLength], cx
0x140033fc4  xor     r8d, r8d; AllocateDestinationString
0x140033fc7  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x140033fcb  call    cs:__imp_RtlDowncaseUnicodeString
0x140033fd2  nop     dword ptr [rax+rax+00h]
0x140033fd7  mov     rax, [rbx+0B0h]
0x140033fde  lea     r8, [rbx+100h]
0x140033fe5  mov     r10d, [rsi+4]
0x140033fe9  lea     r9, [rbx+228h]; LongName
0x140033ff0  mov     rcx, [rbx+0B8h]
0x140033ff7  mov     [rsp+0A0h+Data], r8; Data
0x140033ffc  add     rcx, 408h; Cache
0x140034003  mov     edx, [rax+80h]
0x140034009  lea     r8, [rbp+57h+DestinationString]; ShortName
0x14003400d  xor     rdx, [rax+100h]; DirectoryKey
0x140034014  shr     r10d, 0Bh
0x140034018  and     r10b, 1
0x14003401c  mov     [rsp+0A0h+DataLength], 8; DataLength
0x140034024  mov     [rsp+0A0h+KeyByShortName], r10b; KeyByShortName
0x140034029  call    cs:__imp_FsRtlAddToTunnelCache
0x140034030  nop     dword ptr [rax+rax+00h]
0x140034035  mov     rcx, [rbp+57h+var_28]
0x140034039  xor     rcx, rsp; StackCookie
0x14003403c  call    __security_check_cookie
0x140034041  add     rsp, 88h
0x140034048  pop     rdi
0x140034049  pop     rsi
0x14003404a  pop     rbx
0x14003404b  pop     rbp
0x14003404c  retn
```
