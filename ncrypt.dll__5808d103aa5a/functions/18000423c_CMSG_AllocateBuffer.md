# CMSG_AllocateBuffer

- ea: `0x18000423c`
- end: `0x18000430a`
- name: `CMSG_AllocateBuffer`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003f1c`

## callees

- `0x18000423c`
- `0x180004310`
- `0x18000d02c`
- `0x18000e120`
- `0x18001f175`
- `0x180020010`

## string_xrefs

- `0x1800042b7`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\cmsg.c`
- `0x1800042e7`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\cmsg.c`

## pseudocode

```c
__int64 __fastcall CMSG_AllocateBuffer(__int64 a1, size_t a2, __int64 *a3)
{
  void *v6; // rax
  int v7; // edx
  __int64 v8; // rdi
  unsigned int v9; // eax
  unsigned int v10; // ebx

  *a3 = 0;
  v6 = (void *)(*(__int64 (__fastcall **)(size_t))(a1 + 24))(a2);
  v8 = (__int64)v6;
  if ( v6 )
  {
    memset_0(v6, 0, a2);
    v9 = CMSG_AddBuffer(a1, v8);
    v10 = v9;
    if ( v9 )
    {
      DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c", 129);
      (*(void (__fastcall **)(__int64))(a1 + 32))(v8);
    }
    else
    {
      *a3 = v8;
    }
  }
  else
  {
    v10 = -2146893810;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c",
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c",
        117);
  }
  return v10;
}

```

## disassembly

```asm
0x18000423c  push    rbx
0x18000423e  push    rbp
0x18000423f  push    rsi
0x180004240  push    rdi
0x180004241  sub     rsp, 48h
0x180004245  mov     rbp, rcx
0x180004248  mov     qword ptr [r8], 0
0x18000424f  mov     rcx, rdx
0x180004252  mov     rsi, r8
0x180004255  mov     rbx, rdx
0x180004258  mov     rax, [rbp+18h]
0x18000425c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004261  mov     rdi, rax
0x180004264  test    rax, rax
0x180004267  jz      short loc_180004295
0x180004269  mov     r8, rbx; Size
0x18000426c  xor     edx, edx; Val
0x18000426e  mov     rcx, rax; void *
0x180004271  call    memset_0
0x180004276  mov     rdx, rdi
0x180004279  mov     rcx, rbp
0x18000427c  call    CMSG_AddBuffer
0x180004281  mov     ebx, eax
0x180004283  test    eax, eax
0x180004285  jnz     short loc_1800042E1
0x180004287  mov     [rsi], rdi
0x18000428a  mov     eax, ebx
0x18000428c  add     rsp, 48h
0x180004290  pop     rdi
0x180004291  pop     rsi
0x180004292  pop     rbp
0x180004293  pop     rbx
0x180004294  retn
0x180004295  mov     ebx, 8009000Eh
0x18000429a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042a1  lea     rax, WPP_GLOBAL_Control
0x1800042a8  cmp     rcx, rax
0x1800042ab  jz      short loc_18000428A
0x1800042ad  test    byte ptr [rcx+1Ch], 1
0x1800042b1  jz      short loc_18000428A
0x1800042b3  mov     rcx, [rcx+10h]
0x1800042b7  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800042be  mov     [rsp+68h+var_38], 75h ; 'u'
0x1800042c6  lea     r9, aStatus; "Status"
0x1800042cd  mov     [rsp+68h+var_40], r8
0x1800042d2  mov     [rsp+68h+var_48], 8009000Eh
0x1800042da  call    WPP_SF_sDsd
0x1800042df  jmp     short loc_18000428A
0x1800042e1  mov     r9d, 81h
0x1800042e7  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800042ee  lea     rdx, aStatus; "Status"
0x1800042f5  mov     ecx, eax
0x1800042f7  call    DebugTraceError
0x1800042fc  mov     rax, [rbp+20h]
0x180004300  mov     rcx, rdi
0x180004303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004308  jmp     short loc_18000428A
```
