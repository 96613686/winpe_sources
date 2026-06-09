# GetCanonicalName(ushort const *)

- ea: `0x18001a864`
- end: `0x18001a8f7`
- name: `?GetCanonicalName@@YAPEBGPEBG@Z`
- size: `147`
- prototype: `const unsigned __int16 *__fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008a88`

## callees

- `0x18001a864`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001a87b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001a87b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a8bc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a8bc`

## pseudocode

```c
wchar_t *__fastcall GetCanonicalName(const unsigned __int16 *a1)
{
  wchar_t *v2; // rax
  const WCHAR *v3; // rbx
  unsigned int i; // edi

  if ( a1 )
  {
    v2 = wcsrchr(a1, 0x5Cu);
    if ( v2 )
      v3 = v2 + 1;
    else
      v3 = a1;
    for ( i = 0; i < 0xA; ++i )
    {
      if ( CompareStringOrdinal(v3, -1, (&off_180025DD0)[2 * (int)i], -1, 1) == 2 )
      {
        if ( *((_DWORD *)&off_180025DD0 + 4 * (int)i + 3) == -1 )
          return 0;
        return &aMicrosoftWindo[260 * *((int *)&off_180025DD0 + 4 * (int)i + 3)];
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001a864  push    rbx
0x18001a866  push    rsi
0x18001a867  push    rdi
0x18001a868  push    r14
0x18001a86a  sub     rsp, 38h
0x18001a86e  mov     rdi, rcx
0x18001a871  test    rcx, rcx
0x18001a874  jz      short loc_18001A8EB
0x18001a876  mov     edx, 5Ch ; '\'; Ch
0x18001a87b  call    cs:__imp_wcsrchr
0x18001a881  mov     rbx, rax
0x18001a884  test    rax, rax
0x18001a887  jz      short loc_18001A88F
0x18001a889  add     rbx, 2
0x18001a88d  jmp     short loc_18001A892
0x18001a88f  mov     rbx, rdi
0x18001a892  xor     edi, edi
0x18001a894  lea     r14, off_180025DD0; "{76F3B348-95E1-4B1E-BD1B-E0026D615651}"
0x18001a89b  cmp     edi, 0Ah
0x18001a89e  jnb     short loc_18001A8EB
0x18001a8a0  or      r9d, 0FFFFFFFFh; cchCount2
0x18001a8a4  movsxd  rsi, edi
0x18001a8a7  add     rsi, rsi
0x18001a8aa  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18001a8b2  or      edx, r9d; cchCount1
0x18001a8b5  mov     rcx, rbx; lpString1
0x18001a8b8  mov     r8, [r14+rsi*8]; lpString2
0x18001a8bc  call    cs:__imp_CompareStringOrdinal
0x18001a8c2  cmp     eax, 2
0x18001a8c5  jz      short loc_18001A8CB
0x18001a8c7  inc     edi
0x18001a8c9  jmp     short loc_18001A89B
0x18001a8cb  cmp     dword ptr [r14+rsi*8+0Ch], 0FFFFFFFFh
0x18001a8d1  jz      short loc_18001A8EB
0x18001a8d3  movsxd  rax, dword ptr [r14+rsi*8+0Ch]
0x18001a8d8  lea     rcx, aMicrosoftWindo; "Microsoft.WindowsFirewall"
0x18001a8df  imul    rax, 208h
0x18001a8e6  add     rax, rcx
0x18001a8e9  jmp     short loc_18001A8ED
0x18001a8eb  xor     eax, eax
0x18001a8ed  add     rsp, 38h
0x18001a8f1  pop     r14
0x18001a8f3  pop     rdi
0x18001a8f4  pop     rsi
0x18001a8f5  pop     rbx
0x18001a8f6  retn
```
