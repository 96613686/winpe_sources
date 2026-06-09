# skip_comment

- ea: `0x18001fbe8`
- end: `0x18001fcba`
- name: `skip_comment`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001fcc0`

## callees

- `0x1800022d6`
- `0x18001ec80`
- `0x18001eff4`
- `0x18001f0cc`
- `0x18001fbe8`
- `0x1800200e8`

## pseudocode

```c
unsigned __int64 __fastcall skip_comment(__int64 a1, unsigned __int64 a2)
{
  __int64 v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // r8
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  if ( !(unsigned __int8)is_start_sub_str(L"<!--", L"", a1, a2) )
    return a1;
  v5 = a1 + 8;
  do
  {
    v6 = find_char(v5, a2, 45);
    if ( v6 + 4 >= a2 )
      return a2;
    v5 = v6 + 2;
  }
  while ( *(_WORD *)v5 != 45 );
  if ( *(_WORD *)(v5 + 2) != 62 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_h(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v7, *(unsigned __int16 *)(v5 + 2));
    bad_document::bad_document((bad_document *)pExceptionObject, (const wchar_t *)(v5 + 2));
    throw (bad_document *)pExceptionObject;
  }
  return v5 + 4;
}

```

## disassembly

```asm
0x18001fbe8  mov     [rsp+arg_0], rbx
0x18001fbed  mov     [rsp+arg_8], rsi
0x18001fbf2  push    rdi
0x18001fbf3  sub     rsp, 40h
0x18001fbf7  mov     rdi, rdx
0x18001fbfa  mov     rbx, rcx
0x18001fbfd  mov     r9, rdx
0x18001fc00  mov     r8, rcx
0x18001fc03  lea     rdx, asc_180032B10+8; ""
0x18001fc0a  lea     rcx, asc_180032B10; "<!--"
0x18001fc11  call    is_start_sub_str
0x18001fc16  test    al, al
0x18001fc18  jnz     short loc_18001FC22
0x18001fc1a  mov     rax, rbx
0x18001fc1d  jmp     loc_18001FCAA
0x18001fc22  add     rbx, 8
0x18001fc26  mov     esi, 2Dh ; '-'
0x18001fc2b  mov     r8d, esi
0x18001fc2e  mov     rdx, rdi
0x18001fc31  mov     rcx, rbx
0x18001fc34  call    find_char
0x18001fc39  mov     rbx, rax
0x18001fc3c  add     rax, 4
0x18001fc40  cmp     rax, rdi
0x18001fc43  jnb     short loc_18001FCA7
0x18001fc45  add     rbx, 2
0x18001fc49  cmp     [rbx], si
0x18001fc4c  jnz     short loc_18001FC2B
0x18001fc4e  cmp     word ptr [rbx+2], 3Eh ; '>'
0x18001fc53  jz      short loc_18001FCA1
0x18001fc55  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc5c  lea     rax, WPP_GLOBAL_Control
0x18001fc63  cmp     rcx, rax
0x18001fc66  jz      short loc_18001FC81
0x18001fc68  test    byte ptr [rcx+1Ch], 1
0x18001fc6c  jz      short loc_18001FC81
0x18001fc6e  movzx   r9d, word ptr [rbx+2]
0x18001fc73  mov     edx, 0Ch
0x18001fc78  mov     rcx, [rcx+10h]
0x18001fc7c  call    WPP_SF_h
0x18001fc81  lea     rdx, [rbx+2]; wchar_t *
0x18001fc85  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001fc8a  call    ??0bad_document@@QEAA@PEB_W@Z; bad_document::bad_document(wchar_t const *)
0x18001fc8f  lea     rdx, _TI2?AVbad_document@@; pThrowInfo
0x18001fc96  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001fc9b  call    _CxxThrowException_0
0x18001fca1  lea     rax, [rbx+4]
0x18001fca5  jmp     short loc_18001FCAA
0x18001fca7  mov     rax, rdi
0x18001fcaa  mov     rbx, [rsp+48h+arg_0]
0x18001fcaf  mov     rsi, [rsp+48h+arg_8]
0x18001fcb4  add     rsp, 40h
0x18001fcb8  pop     rdi
0x18001fcb9  retn
```
