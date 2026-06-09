# RasRpcRemoteRasDeleteEntry

- ea: `0x180022d10`
- end: `0x180022e21`
- name: `RasRpcRemoteRasDeleteEntry`
- size: `273`
- prototype: `__int64 __fastcall(__int64, const char *, const char *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180021000`
- `0x180022d10`
- `0x180022eac`
- `0x180023a7c`

## pseudocode

```c
__int64 __fastcall RasRpcRemoteRasDeleteEntry(__int64 a1, const char *a2, const char *a3)
{
  PVOID *v6; // rcx
  const char *v7; // rdx
  const char *v8; // rax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // eax

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v7 = a3;
    v8 = a2;
    if ( !a3 )
      v7 = L"<NULL>";
    if ( !a2 )
      v8 = L"<NULL>";
    WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v8, (__int64)v7);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v12 = RemoteRasDeleteEntry(a1, a2, a3);
    v9 = v12;
    if ( !v12 )
    {
LABEL_20:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_21;
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_21;
    v10 = 41;
    v11 = v12;
LABEL_19:
    WPP_SF_d(v6[2], v10, &WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids, v11);
    goto LABEL_20;
  }
  v9 = 87;
  if ( v6 == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 2u )
  {
    v10 = 40;
    v11 = 87;
    goto LABEL_19;
  }
LABEL_21:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_d(v6[2], 42, &WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180022d10  push    rbx
0x180022d12  push    rsi
0x180022d13  push    rdi
0x180022d14  push    r14
0x180022d16  sub     rsp, 38h
0x180022d1a  mov     rdi, r8
0x180022d1d  mov     rsi, rdx
0x180022d20  mov     rbx, rcx
0x180022d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d2a  lea     r14, WPP_GLOBAL_Control
0x180022d31  cmp     rcx, r14
0x180022d34  jz      short loc_180022D7A
0x180022d36  test    byte ptr [rcx+1Ch], 40h
0x180022d3a  jz      short loc_180022D7A
0x180022d3c  cmp     byte ptr [rcx+19h], 6
0x180022d40  jb      short loc_180022D7A
0x180022d42  mov     rcx, [rcx+10h]; LoggerHandle
0x180022d46  lea     r8, aNull_2; "<NULL>"
0x180022d4d  test    rdi, rdi
0x180022d50  mov     rdx, rdi
0x180022d53  mov     rax, rsi
0x180022d56  mov     r9, rbx
0x180022d59  cmovz   rdx, r8
0x180022d5d  test    rsi, rsi
0x180022d60  mov     [rsp+58h+var_30], rdx; __int64
0x180022d65  cmovz   rax, r8
0x180022d69  mov     [rsp+58h+var_38], rax; __int64
0x180022d6e  call    WPP_SF_qSS
0x180022d73  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d7a  test    rbx, rbx
0x180022d7d  jnz     short loc_180022DA1
0x180022d7f  mov     ebx, 57h ; 'W'
0x180022d84  cmp     rcx, r14
0x180022d87  jz      loc_180022E15
0x180022d8d  test    byte ptr [rcx+1Ch], 40h
0x180022d91  jz      short loc_180022DEC
0x180022d93  cmp     byte ptr [rcx+19h], 2
0x180022d97  jb      short loc_180022DEC
0x180022d99  lea     edx, [rbx-2Fh]
0x180022d9c  mov     r9d, ebx
0x180022d9f  jmp     short loc_180022DD5
0x180022da1  mov     r8, rdi
0x180022da4  mov     rdx, rsi
0x180022da7  mov     rcx, rbx
0x180022daa  call    RemoteRasDeleteEntry
0x180022daf  mov     ebx, eax
0x180022db1  test    eax, eax
0x180022db3  jz      short loc_180022DE5
0x180022db5  mov     rcx, cs:WPP_GLOBAL_Control
0x180022dbc  cmp     rcx, r14
0x180022dbf  jz      short loc_180022E15
0x180022dc1  test    byte ptr [rcx+1Ch], 40h
0x180022dc5  jz      short loc_180022DEC
0x180022dc7  cmp     byte ptr [rcx+19h], 2
0x180022dcb  jb      short loc_180022DEC
0x180022dcd  mov     edx, 29h ; ')'
0x180022dd2  mov     r9d, eax
0x180022dd5  mov     rcx, [rcx+10h]
0x180022dd9  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x180022de0  call    WPP_SF_d
0x180022de5  mov     rcx, cs:WPP_GLOBAL_Control
0x180022dec  cmp     rcx, r14
0x180022def  jz      short loc_180022E15
0x180022df1  test    byte ptr [rcx+1Ch], 40h
0x180022df5  jz      short loc_180022E15
0x180022df7  cmp     byte ptr [rcx+19h], 6
0x180022dfb  jb      short loc_180022E15
0x180022dfd  mov     rcx, [rcx+10h]
0x180022e01  lea     r8, WPP_766d3514d0233fbc21e473ad1a84e9ca_Traceguids
0x180022e08  mov     edx, 2Ah ; '*'
0x180022e0d  mov     r9d, ebx
0x180022e10  call    WPP_SF_d
0x180022e15  mov     eax, ebx
0x180022e17  add     rsp, 38h
0x180022e1b  pop     r14
0x180022e1d  pop     rdi
0x180022e1e  pop     rsi
0x180022e1f  pop     rbx
0x180022e20  retn
```
