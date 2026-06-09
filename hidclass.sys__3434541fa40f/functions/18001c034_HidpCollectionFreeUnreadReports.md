# HidpCollectionFreeUnreadReports

- ea: `0x18001c034`
- end: `0x18001c1ae`
- name: `HidpCollectionFreeUnreadReports`
- size: `378`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019694`
- `0x18004243c`

## callees

- `0x18001c034`
- `0x18001c8a0`
- `0x1800246b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18001c182`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001c182`

## string_xrefs

- `0x18001c140`: `Unread keyboard reports discarded.`

## pseudocode

```c
void __fastcall HidpCollectionFreeUnreadReports(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 **v7; // rdi
  __int64 *v8; // rcx
  __int64 v9; // rax

  if ( *(_DWORD *)(a2 + 64) )
  {
    v4 = MEMORY[0xFFFFF78000000014] - *(_QWORD *)(a2 + 72) + 5000LL;
    v5 = (unsigned __int128)(v4 * (__int128)0x346DC5D63886594BLL) >> 64;
    v6 = v4 / 10000;
    LOBYTE(v5) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdLDDL(WPP_GLOBAL_Control->AttachedDevice, v5, v4, *(_QWORD *)(a1 + 672));
    }
    if ( *(_DWORD *)(a2 + 12) == 2 )
    {
      if ( (unsigned int)v6 > 0xFFFFF )
        LODWORD(v6) = 0xFFFFF;
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
        *(_DWORD *)(a1 + 584) & 1,
        ((_DWORD)v6 << 12)
      | *(_DWORD *)(a2 + 64) & 0xF
      | (16 * (*(_BYTE *)(a1 + 588) & 1 | (2 * (*(_DWORD *)(a1 + 584) & 1u)))),
        *(unsigned __int16 *)(a1 + 110) | (*(unsigned __int16 *)(a1 + 108) << 16),
        "Unread keyboard reports discarded.");
    }
    if ( *(_DWORD *)(a2 + 64) )
    {
      v7 = (__int64 **)(a2 + 48);
      do
      {
        v8 = *v7;
        if ( (__int64 **)(*v7)[1] != v7 || (v9 = *v8, *(__int64 **)(*v8 + 8) != v8) )
          __fastfail(3u);
        *(_QWORD *)(a2 + 48) = v9;
        *(_QWORD *)(v9 + 8) = v7;
        ExFreePoolWithTag(v8, 0);
      }
      while ( (*(_DWORD *)(a2 + 64))-- != 1 );
    }
  }
}

```

## disassembly

```asm
0x18001c034  mov     [rsp+arg_0], rbx
0x18001c039  mov     [rsp+arg_8], rsi
0x18001c03e  push    rdi
0x18001c03f  sub     rsp, 70h
0x18001c043  cmp     dword ptr [rdx+40h], 0
0x18001c047  mov     rbx, rdx
0x18001c04a  mov     rsi, rcx
0x18001c04d  jz      loc_18001C194
0x18001c053  mov     r8, 0FFFFF78000000014h
0x18001c05d  mov     rax, 346DC5D63886594Bh
0x18001c067  mov     r8, [r8]
0x18001c06a  sub     r8, [rdx+48h]
0x18001c06e  add     r8, 1388h
0x18001c075  imul    r8
0x18001c078  mov     rdi, rdx
0x18001c07b  sar     rdi, 0Bh
0x18001c07f  mov     rax, rdi
0x18001c082  shr     rax, 3Fh
0x18001c086  add     rdi, rax
0x18001c089  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c090  lea     rax, WPP_GLOBAL_Control
0x18001c097  cmp     rcx, rax
0x18001c09a  jz      short loc_18001C0AD
0x18001c09c  mov     eax, [rcx+2Ch]
0x18001c09f  test    al, 2
0x18001c0a1  jz      short loc_18001C0AD
0x18001c0a3  cmp     byte ptr [rcx+29h], 3
0x18001c0a7  jb      short loc_18001C0AD
0x18001c0a9  mov     dl, 1
0x18001c0ab  jmp     short loc_18001C0AF
0x18001c0ad  xor     dl, dl
0x18001c0af  lea     rax, WPP_RECORDER_INITIALIZED
0x18001c0b6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001c0bd  setnz   r8b
0x18001c0c1  test    dl, dl
0x18001c0c3  jnz     short loc_18001C0CA
0x18001c0c5  test    r8b, r8b
0x18001c0c8  jz      short loc_18001C108
0x18001c0ca  movzx   eax, byte ptr [rsi+24Ch]
0x18001c0d1  mov     r9, [rsi+2A0h]
0x18001c0d8  mov     rcx, [rcx+18h]
0x18001c0dc  mov     [rsp+78h+var_10], edi
0x18001c0e0  mov     [rsp+78h+var_18], eax
0x18001c0e4  mov     eax, [rsi+248h]
0x18001c0ea  mov     [rsp+78h+var_20], eax
0x18001c0ee  mov     eax, [rbx+40h]
0x18001c0f1  mov     [rsp+78h+var_28], eax
0x18001c0f5  mov     eax, [rbx]
0x18001c0f7  mov     [rsp+78h+var_30], eax
0x18001c0fb  mov     rax, [rsi]
0x18001c0fe  mov     [rsp+78h+var_38], rax
0x18001c103  call    WPP_RECORDER_AND_TRACE_SF_qdLDDL
0x18001c108  cmp     dword ptr [rbx+0Ch], 2
0x18001c10c  jnz     short loc_18001C15C
0x18001c10e  mov     ecx, [rsi+248h]
0x18001c114  movzx   eax, byte ptr [rsi+24Ch]
0x18001c11b  and     ecx, 1
0x18001c11e  and     eax, 1
0x18001c121  lea     edx, [rcx+rcx]
0x18001c124  or      edx, eax
0x18001c126  mov     eax, [rbx+40h]
0x18001c129  and     eax, 0Fh
0x18001c12c  shl     edx, 4
0x18001c12f  or      edx, eax
0x18001c131  mov     eax, 0FFFFFh
0x18001c136  cmp     edi, eax
0x18001c138  cmova   edi, eax
0x18001c13b  movzx   r8d, word ptr [rsi+6Ch]; __annotation("Debug", "TelemetryAssert", "FALSE", "Unread keyboard reports discarded.")
0x18001c140  lea     r9, aUnreadKeyboard; "Unread keyboard reports discarded."
0x18001c147  movzx   eax, word ptr [rsi+6Eh]
0x18001c14b  shl     r8d, 10h
0x18001c14f  shl     edi, 0Ch
0x18001c152  or      r8d, eax
0x18001c155  or      edx, edi
0x18001c157  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x18001c15c  cmp     dword ptr [rbx+40h], 0
0x18001c160  jz      short loc_18001C194
0x18001c162  lea     rdi, [rbx+30h]
0x18001c166  mov     rcx, [rdi]; P
0x18001c169  cmp     [rcx+8], rdi
0x18001c16d  jnz     short loc_18001C1A7
0x18001c16f  mov     rax, [rcx]
0x18001c172  cmp     [rax+8], rcx
0x18001c176  jnz     short loc_18001C1A7
0x18001c178  mov     [rbx+30h], rax
0x18001c17c  xor     edx, edx; Tag
0x18001c17e  mov     [rax+8], rdi
0x18001c182  call    cs:__imp_ExFreePoolWithTag
0x18001c189  nop     dword ptr [rax+rax+00h]
0x18001c18e  sub     dword ptr [rbx+40h], 1
0x18001c192  jnz     short loc_18001C166
0x18001c194  lea     r11, [rsp+78h+var_8]
0x18001c199  mov     rbx, [r11+10h]
0x18001c19d  mov     rsi, [r11+18h]
0x18001c1a1  mov     rsp, r11
0x18001c1a4  pop     rdi
0x18001c1a5  retn
0x18001c1a7  mov     ecx, 3
0x18001c1ac  int     29h; Win8: RtlFailFast(ecx)
```
