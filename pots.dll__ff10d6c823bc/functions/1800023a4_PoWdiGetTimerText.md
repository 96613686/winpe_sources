# PoWdiGetTimerText

- ea: `0x1800023a4`
- end: `0x1800024e2`
- name: `PoWdiGetTimerText`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180001d10`

## callees

- `0x180001ec8`
- `0x1800023a4`
- `0x180002530`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180002493`
- `msvcrt!wcsrchr` at `0x180002493`
- `ntdll!RtlInitUnicodeString` at `0x1800024b7`
- `ntdll!RtlInitUnicodeString` at `0x1800024c4`
- `ntdll!RtlInitUnicodeString` at `0x1800024d1`
- `ntdll!RtlInitUnicodeString` at `0x1800024b7`
- `ntdll!RtlInitUnicodeString` at `0x1800024c4`
- `ntdll!RtlInitUnicodeString` at `0x1800024d1`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18000243f`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18000243f`

## pseudocode

```c
void __fastcall PoWdiGetTimerText(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  const wchar_t *v3; // rbp
  const WCHAR *v4; // r14
  const WCHAR *UserSuppliedReason; // rdi
  __int64 v7; // rax
  __int64 v8; // rax
  wchar_t *v9; // rax
  __int128 v10; // [rsp+20h] [rbp-48h] BYREF
  const WCHAR *v11; // [rsp+30h] [rbp-38h]

  v2 = a1 + 8;
  v3 = 0;
  v11 = 0;
  v4 = 0;
  v10 = 0;
  if ( *(_QWORD *)(a1 + 8) )
  {
    v7 = *(_QWORD *)(a1 + 24);
    UserSuppliedReason = 0;
    if ( *(_DWORD *)(a1 + 16) )
    {
      if ( v7 )
        v3 = (const wchar_t *)PoWdiCopyString((_WORD *)(v7 + v2));
      if ( *(_DWORD *)(v2 + 8) == 2 )
      {
        *(_QWORD *)&v10 = *(_QWORD *)(v2 + 24);
        if ( !(unsigned int)I_QueryTagInformation(0, 1, &v10) )
          v4 = v11;
      }
    }
    else
    {
      if ( v7 )
        v3 = (const wchar_t *)PoWdiCopyString((_WORD *)(v7 + v2));
      v8 = *(_QWORD *)(v2 + 24);
      if ( v8 )
        v4 = (const WCHAR *)PoWdiCopyString((_WORD *)(v8 + v2));
    }
    if ( *(_QWORD *)(v2 + 32) )
    {
      UserSuppliedReason = (const WCHAR *)PoWdiGetUserSuppliedReason(v2);
      if ( UserSuppliedReason )
        *(_DWORD *)(a2 + 144) = 1;
    }
  }
  else
  {
    UserSuppliedReason = &SourceString;
  }
  *(_DWORD *)(a2 + 68) = (*(_DWORD *)(a2 + 4) & 0x40000) != 0 ? 8 : 6;
  if ( !UserSuppliedReason )
  {
    if ( v3 )
    {
      v9 = wcsrchr(v3, 0x5Cu);
      UserSuppliedReason = v3;
      if ( v9 )
        UserSuppliedReason = v9 + 1;
    }
    else
    {
      *(_DWORD *)(a2 + 68) = 7;
    }
  }
  RtlInitUnicodeString((PUNICODE_STRING)(a2 + 72), UserSuppliedReason);
  RtlInitUnicodeString((PUNICODE_STRING)(a2 + 88), v3);
  RtlInitUnicodeString((PUNICODE_STRING)(a2 + 104), v4);
}

```

## disassembly

```asm
0x1800023a4  push    rbx
0x1800023a6  push    rbp
0x1800023a7  push    rsi
0x1800023a8  push    rdi
0x1800023a9  push    r14
0x1800023ab  sub     rsp, 40h
0x1800023af  xor     eax, eax
0x1800023b1  lea     rbx, [rcx+8]
0x1800023b5  xor     ebp, ebp
0x1800023b7  mov     [rsp+68h+var_38], rax
0x1800023bc  xor     r14d, r14d
0x1800023bf  xorps   xmm0, xmm0
0x1800023c2  mov     rsi, rdx
0x1800023c5  movups  [rsp+68h+var_48], xmm0
0x1800023ca  cmp     [rbx], rax
0x1800023cd  jnz     short loc_1800023DB
0x1800023cf  lea     rdi, SourceString
0x1800023d6  jmp     loc_18000246D
0x1800023db  mov     rax, [rbx+10h]
0x1800023df  xor     edi, edi
0x1800023e1  cmp     [rbx+8], edi
0x1800023e4  jnz     short loc_18000240E
0x1800023e6  test    rax, rax
0x1800023e9  jz      short loc_1800023F7
0x1800023eb  lea     rcx, [rax+rbx]; Src
0x1800023ef  call    PoWdiCopyString
0x1800023f4  mov     rbp, rax
0x1800023f7  mov     rax, [rbx+18h]
0x1800023fb  test    rax, rax
0x1800023fe  jz      short loc_18000244D
0x180002400  lea     rcx, [rax+rbx]; Src
0x180002404  call    PoWdiCopyString
0x180002409  mov     r14, rax
0x18000240c  jmp     short loc_18000244D
0x18000240e  test    rax, rax
0x180002411  jz      short loc_18000241F
0x180002413  lea     rcx, [rax+rbx]; Src
0x180002417  call    PoWdiCopyString
0x18000241c  mov     rbp, rax
0x18000241f  cmp     dword ptr [rbx+8], 2
0x180002423  jnz     short loc_18000244D
0x180002425  mov     eax, [rbx+18h]
0x180002428  lea     r8, [rsp+68h+var_48]
0x18000242d  mov     dword ptr [rsp+68h+var_48], eax
0x180002431  mov     edx, 1
0x180002436  mov     eax, [rbx+1Ch]
0x180002439  xor     ecx, ecx
0x18000243b  mov     dword ptr [rsp+68h+var_48+4], eax
0x18000243f  call    cs:__imp_I_QueryTagInformation
0x180002445  test    eax, eax
0x180002447  cmovz   r14, [rsp+68h+var_38]
0x18000244d  cmp     [rbx+20h], rdi
0x180002451  jz      short loc_18000246D
0x180002453  mov     rcx, rbx
0x180002456  call    PoWdiGetUserSuppliedReason
0x18000245b  mov     rdi, rax
0x18000245e  test    rax, rax
0x180002461  jz      short loc_18000246D
0x180002463  mov     dword ptr [rsi+90h], 1
0x18000246d  mov     ecx, [rsi+4]
0x180002470  and     ecx, 40000h
0x180002476  neg     ecx
0x180002478  sbb     edx, edx
0x18000247a  and     edx, 2
0x18000247d  add     edx, 6
0x180002480  mov     [rsi+44h], edx
0x180002483  test    rdi, rdi
0x180002486  jnz     short loc_1800024B0
0x180002488  test    rbp, rbp
0x18000248b  jz      short loc_1800024A9
0x18000248d  lea     edx, [rdi+5Ch]; Ch
0x180002490  mov     rcx, rbp; Str
0x180002493  call    cs:__imp_wcsrchr
0x180002499  test    rax, rax
0x18000249c  mov     rdi, rbp
0x18000249f  lea     rcx, [rax+2]
0x1800024a3  cmovnz  rdi, rcx
0x1800024a7  jmp     short loc_1800024B0
0x1800024a9  mov     dword ptr [rsi+44h], 7
0x1800024b0  lea     rcx, [rsi+48h]; DestinationString
0x1800024b4  mov     rdx, rdi; SourceString
0x1800024b7  call    cs:__imp_RtlInitUnicodeString
0x1800024bd  lea     rcx, [rsi+58h]; DestinationString
0x1800024c1  mov     rdx, rbp; SourceString
0x1800024c4  call    cs:__imp_RtlInitUnicodeString
0x1800024ca  lea     rcx, [rsi+68h]; DestinationString
0x1800024ce  mov     rdx, r14; SourceString
0x1800024d1  call    cs:__imp_RtlInitUnicodeString
0x1800024d7  add     rsp, 40h
0x1800024db  pop     r14
0x1800024dd  pop     rdi
0x1800024de  pop     rsi
0x1800024df  pop     rbp
0x1800024e0  pop     rbx
0x1800024e1  retn
```
