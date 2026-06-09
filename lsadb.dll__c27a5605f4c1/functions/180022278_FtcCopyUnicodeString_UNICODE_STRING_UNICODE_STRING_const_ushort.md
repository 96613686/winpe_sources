# FtcCopyUnicodeString(_UNICODE_STRING *,_UNICODE_STRING const *,ushort *)

- ea: `0x180022278`
- end: `0x180022320`
- name: `?FtcCopyUnicodeString@@YAEPEAU_UNICODE_STRING@@PEBU1@PEAG@Z`
- size: `168`
- prototype: `unsigned __int8 __fastcall(PUNICODE_STRING DestinationString, PCUNICODE_STRING SourceString, unsigned __int16 *)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180022580`
- `0x180025160`
- `0x18002934c`
- `0x1800294ac`
- `0x1800295ac`
- `0x18002970c`
- `0x180029928`
- `0x18002a43c`
- `0x18002a5ac`
- `0x18002a73c`

## callees

- `0x18000fd40`
- `0x180022278`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800222b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800222b7`
- `ntdll!RtlCopyUnicodeString` at `0x180022308`
- `ntdll!RtlCopyUnicodeString` at `0x180022308`

## pseudocode

```c
unsigned __int8 __fastcall FtcCopyUnicodeString(
        PUNICODE_STRING DestinationString,
        PCUNICODE_STRING SourceString,
        unsigned __int16 *a3)
{
  USHORT v5; // ax
  WCHAR *v6; // rax

  if ( !SourceString->Length )
  {
    DestinationString->Buffer = 0;
    DestinationString->MaximumLength = 0;
    goto LABEL_11;
  }
  v5 = SourceString->Length + 2;
  if ( v5 < SourceString->Length )
  {
    DestinationString->MaximumLength = -1;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, 3221225621LL);
    return 0;
  }
  DestinationString->MaximumLength = v5;
  if ( !a3 )
  {
    v6 = (WCHAR *)LocalAlloc(0x40u, v5);
    DestinationString->Buffer = v6;
    if ( v6 )
      goto LABEL_11;
    return 0;
  }
  DestinationString->Buffer = a3;
LABEL_11:
  RtlCopyUnicodeString(DestinationString, SourceString);
  return 1;
}

```

## disassembly

```asm
0x180022278  mov     [rsp+arg_0], rbx
0x18002227d  mov     [rsp+arg_8], rsi
0x180022282  push    rdi
0x180022283  sub     rsp, 20h
0x180022287  xor     esi, esi
0x180022289  mov     rdi, rdx
0x18002228c  mov     rbx, rcx
0x18002228f  cmp     [rdx], si
0x180022292  jbe     short loc_1800222FA
0x180022294  movzx   eax, word ptr [rdx]
0x180022297  add     ax, 2
0x18002229b  cmp     ax, [rdx]
0x18002229e  jb      short loc_1800222C8
0x1800222a0  mov     [rcx+2], ax
0x1800222a4  test    r8, r8
0x1800222a7  jz      short loc_1800222AF
0x1800222a9  mov     [rcx+8], r8
0x1800222ad  jmp     short loc_180022302
0x1800222af  movzx   edx, ax; uBytes
0x1800222b2  mov     ecx, 40h ; '@'; uFlags
0x1800222b7  call    cs:__imp_LocalAlloc
0x1800222bd  mov     [rbx+8], rax
0x1800222c1  test    rax, rax
0x1800222c4  jnz     short loc_180022302
0x1800222c6  jmp     short loc_1800222F6
0x1800222c8  mov     word ptr [rcx+2], 0FFFFh
0x1800222ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222d5  test    byte ptr [rcx+1Ch], 8
0x1800222d9  jz      short loc_1800222F6
0x1800222db  mov     rcx, [rcx+10h]
0x1800222df  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x1800222e6  mov     edx, 0Ah
0x1800222eb  mov     r9d, 0C0000095h
0x1800222f1  call    WPP_SF_d
0x1800222f6  xor     al, al
0x1800222f8  jmp     short loc_180022310
0x1800222fa  mov     [rcx+8], rsi
0x1800222fe  mov     [rcx+2], si
0x180022302  mov     rdx, rdi; SourceString
0x180022305  mov     rcx, rbx; DestinationString
0x180022308  call    cs:__imp_RtlCopyUnicodeString
0x18002230e  mov     al, 1
0x180022310  mov     rbx, [rsp+28h+arg_0]
0x180022315  mov     rsi, [rsp+28h+arg_8]
0x18002231a  add     rsp, 20h
0x18002231e  pop     rdi
0x18002231f  retn
```
