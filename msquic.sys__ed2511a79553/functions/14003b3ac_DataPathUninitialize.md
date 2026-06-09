# DataPathUninitialize

- ea: `0x14003b3ac`
- end: `0x14003b4cb`
- name: `DataPathUninitialize`
- size: `287`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140034e2c`

## callees

- `0x14003b3ac`

## import_xrefs

- `NETIO!WskDeregister` at `0x14003b3dd`
- `NETIO!WskDeregister` at `0x14003b3dd`
- `NETIO!WskReleaseProviderNPI` at `0x14003b3cd`
- `NETIO!WskReleaseProviderNPI` at `0x14003b3cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b4ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b4ae`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b408`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b41e`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b434`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b44a`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b460`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b476`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b48c`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b408`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b41e`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b434`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b44a`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b460`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b476`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14003b48c`

## pseudocode

```c
void __fastcall DataPathUninitialize(struct _WSK_REGISTRATION *P)
{
  unsigned int v2; // esi
  __int64 v3; // rbx

  if ( P )
  {
    v2 = 0;
    WskReleaseProviderNPI(P + 3);
    WskDeregister(P + 3);
    if ( LODWORD(P[5].ReservedRegistrationContext) )
    {
      do
      {
        v3 = 688LL * v2;
        ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)((char *)&P[6] + v3));
        ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)((char *)&P[10] + v3));
        ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)((char *)&P[14] + v3));
        ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)((char *)&P[18] + v3));
        ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)((char *)&P[22] + v3));
        ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)((char *)&P[26] + v3));
        ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)((char *)&P[30] + v3));
        ++v2;
      }
      while ( v2 < LODWORD(P[5].ReservedRegistrationContext) );
    }
    ExFreePoolWithTag(P, 0x42326351u);
  }
}

```

## disassembly

```asm
0x14003b3ac  test    rcx, rcx
0x14003b3af  jz      locret_14003B4C9
0x14003b3b5  mov     [rsp+arg_0], rbx
0x14003b3ba  mov     [rsp+arg_8], rsi
0x14003b3bf  push    rdi
0x14003b3c0  sub     rsp, 20h
0x14003b3c4  mov     rdi, rcx
0x14003b3c7  xor     esi, esi
0x14003b3c9  add     rcx, 48h ; 'H'; WskRegistration
0x14003b3cd  call    cs:__imp_WskReleaseProviderNPI
0x14003b3d4  nop     dword ptr [rax+rax+00h]
0x14003b3d9  lea     rcx, [rdi+48h]; WskRegistration
0x14003b3dd  call    cs:__imp_WskDeregister
0x14003b3e4  nop     dword ptr [rax+rax+00h]
0x14003b3e9  cmp     [rdi+80h], esi
0x14003b3ef  jbe     loc_14003B4A6
0x14003b3f5  mov     eax, esi
0x14003b3f7  lea     rcx, [rdi+90h]
0x14003b3fe  imul    rbx, rax, 2B0h
0x14003b405  add     rcx, rbx; Lookaside
0x14003b408  call    cs:__imp_ExDeleteLookasideListEx
0x14003b40f  nop     dword ptr [rax+rax+00h]
0x14003b414  lea     rcx, [rdi+0F0h]
0x14003b41b  add     rcx, rbx; Lookaside
0x14003b41e  call    cs:__imp_ExDeleteLookasideListEx
0x14003b425  nop     dword ptr [rax+rax+00h]
0x14003b42a  lea     rcx, [rdi+150h]
0x14003b431  add     rcx, rbx; Lookaside
0x14003b434  call    cs:__imp_ExDeleteLookasideListEx
0x14003b43b  nop     dword ptr [rax+rax+00h]
0x14003b440  lea     rcx, [rdi+1B0h]
0x14003b447  add     rcx, rbx; Lookaside
0x14003b44a  call    cs:__imp_ExDeleteLookasideListEx
0x14003b451  nop     dword ptr [rax+rax+00h]
0x14003b456  lea     rcx, [rdi+210h]
0x14003b45d  add     rcx, rbx; Lookaside
0x14003b460  call    cs:__imp_ExDeleteLookasideListEx
0x14003b467  nop     dword ptr [rax+rax+00h]
0x14003b46c  lea     rcx, [rdi+270h]
0x14003b473  add     rcx, rbx; Lookaside
0x14003b476  call    cs:__imp_ExDeleteLookasideListEx
0x14003b47d  nop     dword ptr [rax+rax+00h]
0x14003b482  lea     rcx, [rdi+2D0h]
0x14003b489  add     rcx, rbx; Lookaside
0x14003b48c  call    cs:__imp_ExDeleteLookasideListEx
0x14003b493  nop     dword ptr [rax+rax+00h]
0x14003b498  inc     esi
0x14003b49a  cmp     esi, [rdi+80h]
0x14003b4a0  jb      loc_14003B3F5
0x14003b4a6  mov     edx, 42326351h; Tag
0x14003b4ab  mov     rcx, rdi; P
0x14003b4ae  call    cs:__imp_ExFreePoolWithTag
0x14003b4b5  nop     dword ptr [rax+rax+00h]
0x14003b4ba  mov     rbx, [rsp+28h+arg_0]
0x14003b4bf  mov     rsi, [rsp+28h+arg_8]
0x14003b4c4  add     rsp, 20h
0x14003b4c8  pop     rdi
0x14003b4c9  retn
```
