# QueryIsAppContainer

- ea: `0x140034048`
- end: `0x1400340c6`
- name: `QueryIsAppContainer`
- size: `126`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001eec`
- `0x14000a060`
- `0x140032148`

## callees

- `0x140034048`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x140034099`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140034099`
- `ntoskrnl!SeQueryInformationToken` at `0x140034088`
- `ntoskrnl!SeQueryInformationToken` at `0x140034088`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14003406c`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14003406c`

## pseudocode

```c
__int64 __fastcall QueryIsAppContainer(struct _KPROCESS *a1, bool *a2)
{
  NTSTATUS v3; // edi
  PACCESS_TOKEN v4; // rbx
  PVOID TokenInformation; // [rsp+30h] [rbp+8h] BYREF

  LODWORD(TokenInformation) = 0;
  v3 = -1073741823;
  if ( a1 )
  {
    v4 = PsReferencePrimaryToken(a1);
    v3 = SeQueryInformationToken(v4, TokenIsAppContainer, &TokenInformation);
    PsDereferencePrimaryToken(v4);
    if ( v3 >= 0 )
      *a2 = (_DWORD)TokenInformation != 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140034048  mov     [rsp+arg_8], rbx
0x14003404d  mov     [rsp+arg_10], rsi
0x140034052  push    rdi
0x140034053  sub     rsp, 20h
0x140034057  mov     dword ptr [rsp+28h+TokenInformation], 0
0x14003405f  mov     rsi, rdx
0x140034062  mov     edi, 0C0000001h
0x140034067  test    rcx, rcx
0x14003406a  jz      short loc_1400340B3
0x14003406c  call    cs:__imp_PsReferencePrimaryToken
0x140034073  nop     dword ptr [rax+rax+00h]
0x140034078  lea     r8, [rsp+28h+TokenInformation]; TokenInformation
0x14003407d  mov     edx, 1Dh; TokenInformationClass
0x140034082  mov     rcx, rax; Token
0x140034085  mov     rbx, rax
0x140034088  call    cs:__imp_SeQueryInformationToken
0x14003408f  nop     dword ptr [rax+rax+00h]
0x140034094  mov     rcx, rbx; PrimaryToken
0x140034097  mov     edi, eax
0x140034099  call    cs:__imp_PsDereferencePrimaryToken
0x1400340a0  nop     dword ptr [rax+rax+00h]
0x1400340a5  test    edi, edi
0x1400340a7  js      short loc_1400340B3
0x1400340a9  cmp     dword ptr [rsp+28h+TokenInformation], 0
0x1400340ae  setnz   cl
0x1400340b1  mov     [rsi], cl
0x1400340b3  mov     rbx, [rsp+28h+arg_8]
0x1400340b8  mov     eax, edi
0x1400340ba  mov     rsi, [rsp+28h+arg_10]
0x1400340bf  add     rsp, 20h
0x1400340c3  pop     rdi
0x1400340c4  retn
```
