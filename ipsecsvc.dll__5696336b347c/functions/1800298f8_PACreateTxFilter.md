# PACreateTxFilter

- ea: `0x1800298f8`
- end: `0x180029bd3`
- name: `PACreateTxFilter`
- size: `731`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18002a868`

## callees

- `0x180006f00`
- `0x18000964c`
- `0x18000c828`
- `0x18000e510`
- `0x18001cc50`
- `0x180029418`
- `0x180029448`
- `0x180029504`
- `0x1800298f8`
- `0x180029fb8`
- `0x1800433c4`
- `0x180043460`
- `0x18004d090`

## pseudocode

```c
__int64 __fastcall PACreateTxFilter(_OWORD *a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  unsigned int *v9; // rbx
  unsigned int v10; // esi
  _QWORD *v11; // rcx
  __int64 v12; // rbp
  unsigned int IpVersionFromFilterSpec; // eax
  unsigned __int16 *v14; // rcx
  unsigned __int16 *v15; // rax
  __int64 v16; // rdx
  unsigned __int16 v17; // ax
  unsigned __int16 *v18; // rax
  __int64 result; // rax
  __int64 v20; // rcx
  wchar_t pszDest[512]; // [rsp+30h] [rbp-448h] BYREF

  v9 = (unsigned int *)IpsecAllocMem(0xB8u);
  if ( !v9 )
  {
    v10 = 8;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_49d531a97551358b2c2543ad66978cd1_Traceguids, 8);
      v11 = WPP_GLOBAL_Control;
    }
    v12 = a3 + 24;
    goto LABEL_21;
  }
  IpVersionFromFilterSpec = GetIpVersionFromFilterSpec(a3);
  *v9 = MapProtocolVersion(IpVersionFromFilterSpec);
  v12 = a3 + 24;
  *(_OWORD *)(v9 + 1) = *(_OWORD *)(a3 + 24);
  v14 = *(unsigned __int16 **)(a3 + 16);
  if ( v14 && *v14 )
  {
    v15 = IpsecAllocStr(v14);
    *((_QWORD *)v9 + 3) = v15;
    if ( !v15 )
    {
      v10 = 8;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v16 = 20;
LABEL_20:
          WPP_SF_d(v11[2], v16, WPP_49d531a97551358b2c2543ad66978cd1_Traceguids, v10);
          v11 = WPP_GLOBAL_Control;
          goto LABEL_21;
        }
        goto LABEL_21;
      }
      goto LABEL_24;
    }
LABEL_27:
    PASetInterfaceType(*(unsigned int *)(a2 + 40), v9 + 8);
    v9[9] = *(_DWORD *)(a3 + 40);
    v20 = *v9;
    v9[10] = 0;
    PASetAddress(v20, a3 + 44, v9 + 12);
    PASetAddress(*v9, a3 + 84, v9 + 22);
    v9[32] = 1;
    v9[33] = *(_DWORD *)(a3 + 140);
    v9[34] = *(_DWORD *)(a3 + 124);
    *((_WORD *)v9 + 70) = *(_WORD *)(a3 + 128);
    *((_WORD *)v9 + 71) = *(_WORD *)(a3 + 130);
    v9[36] = *(_DWORD *)(a3 + 132);
    *((_WORD *)v9 + 74) = *(_WORD *)(a3 + 136);
    *((_WORD *)v9 + 75) = *(_WORD *)(a3 + 138);
    SetFilterActions(a4, v9 + 38, v9 + 39);
    *((_QWORD *)v9 + 20) = 0;
    result = 0;
    *(_OWORD *)(v9 + 42) = *a1;
    *a5 = v9;
    return result;
  }
  ++gdwTxFilterCounter;
  v17 = StringCchPrintfW(pszDest, 0x200u, L"%d");
  v10 = v17;
  if ( !v17 )
  {
    v18 = IpsecAllocStr(pszDest);
    *((_QWORD *)v9 + 3) = v18;
    if ( !v18 )
    {
      v10 = 8;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v16 = 22;
          goto LABEL_20;
        }
        goto LABEL_21;
      }
      goto LABEL_24;
    }
    goto LABEL_27;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v16 = 21;
      goto LABEL_20;
    }
LABEL_21:
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
      WPP_SF__guid_D(v11[2], 25, WPP_49d531a97551358b2c2543ad66978cd1_Traceguids, v12, v10);
  }
LABEL_24:
  if ( v9 )
    PAFreeTxFilter(v9);
  *a5 = 0;
  return v10;
}

```

## disassembly

```asm
0x1800298f8  mov     [rsp+arg_0], rbx
0x1800298fd  push    rbp
0x1800298fe  push    rsi
0x1800298ff  push    rdi
0x180029900  push    r12
0x180029902  push    r13
0x180029904  push    r14
0x180029906  push    r15
0x180029908  sub     rsp, 440h
0x18002990f  mov     rax, cs:__security_cookie
0x180029916  xor     rax, rsp
0x180029919  mov     [rsp+478h+var_48], rax
0x180029921  mov     r15, [rsp+478h+arg_20]
0x180029929  mov     r12, rcx
0x18002992c  mov     ecx, 0B8h
0x180029931  mov     r13, r9
0x180029934  mov     r14, r8
0x180029937  mov     rdi, rdx
0x18002993a  call    IpsecAllocMem
0x18002993f  xor     esi, esi
0x180029941  mov     rbx, rax
0x180029944  test    rax, rax
0x180029947  jnz     short loc_18002998B
0x180029949  lea     esi, [rax+8]
0x18002994c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029953  lea     rdi, WPP_GLOBAL_Control
0x18002995a  cmp     rcx, rdi
0x18002995d  jz      short loc_180029982
0x18002995f  test    byte ptr [rcx+1Ch], 10h
0x180029963  jz      short loc_180029982
0x180029965  mov     rcx, [rcx+10h]
0x180029969  lea     edx, [rax+13h]
0x18002996c  mov     r9d, esi
0x18002996f  lea     r8, WPP_49d531a97551358b2c2543ad66978cd1_Traceguids
0x180029976  call    WPP_SF_d
0x18002997b  mov     rcx, cs:WPP_GLOBAL_Control
0x180029982  lea     rbp, [r14+18h]
0x180029986  jmp     loc_180029A95
0x18002998b  mov     rcx, r14
0x18002998e  call    GetIpVersionFromFilterSpec
0x180029993  mov     ecx, eax
0x180029995  call    MapProtocolVersion
0x18002999a  mov     [rbx], eax
0x18002999c  lea     rbp, [r14+18h]
0x1800299a0  movups  xmm0, xmmword ptr [rbp+0]
0x1800299a4  movdqu  xmmword ptr [rbx+4], xmm0
0x1800299a9  mov     rcx, [r14+10h]; unsigned __int16 *
0x1800299ad  test    rcx, rcx
0x1800299b0  jz      short loc_1800299F5
0x1800299b2  cmp     [rcx], si
0x1800299b5  jz      short loc_1800299F5
0x1800299b7  call    IpsecAllocStr
0x1800299bc  mov     [rbx+18h], rax
0x1800299c0  test    rax, rax
0x1800299c3  jnz     loc_180029AD7
0x1800299c9  lea     esi, [rax+8]
0x1800299cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800299d3  lea     rdi, WPP_GLOBAL_Control
0x1800299da  cmp     rcx, rdi
0x1800299dd  jz      loc_180029ABC
0x1800299e3  test    byte ptr [rcx+1Ch], 10h
0x1800299e7  jz      loc_180029A95
0x1800299ed  lea     edx, [rax+14h]
0x1800299f0  jmp     loc_180029A7B
0x1800299f5  mov     r9d, cs:gdwTxFilterCounter
0x1800299fc  lea     r8, aD; "%d"
0x180029a03  inc     r9d
0x180029a06  lea     rcx, [rsp+478h+pszDest]; pszDest
0x180029a0b  mov     edx, 200h; cchDest
0x180029a10  mov     cs:gdwTxFilterCounter, r9d
0x180029a17  call    StringCchPrintfW
0x180029a1c  movzx   esi, ax
0x180029a1f  test    esi, esi
0x180029a21  jz      short loc_180029A47
0x180029a23  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a2a  lea     rdi, WPP_GLOBAL_Control
0x180029a31  cmp     rcx, rdi
0x180029a34  jz      loc_180029ABC
0x180029a3a  test    byte ptr [rcx+1Ch], 10h
0x180029a3e  jz      short loc_180029A95
0x180029a40  mov     edx, 15h
0x180029a45  jmp     short loc_180029A7B
0x180029a47  lea     rcx, [rsp+478h+pszDest]; unsigned __int16 *
0x180029a4c  call    IpsecAllocStr
0x180029a51  xor     esi, esi
0x180029a53  mov     [rbx+18h], rax
0x180029a57  test    rax, rax
0x180029a5a  jnz     short loc_180029AD7
0x180029a5c  lea     esi, [rax+8]
0x180029a5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a66  lea     rdi, WPP_GLOBAL_Control
0x180029a6d  cmp     rcx, rdi
0x180029a70  jz      short loc_180029ABC
0x180029a72  test    byte ptr [rcx+1Ch], 10h
0x180029a76  jz      short loc_180029A95
0x180029a78  lea     edx, [rax+16h]
0x180029a7b  mov     rcx, [rcx+10h]
0x180029a7f  lea     r8, WPP_49d531a97551358b2c2543ad66978cd1_Traceguids
0x180029a86  mov     r9d, esi
0x180029a89  call    WPP_SF_d
0x180029a8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a95  cmp     rcx, rdi
0x180029a98  jz      short loc_180029ABC
0x180029a9a  test    byte ptr [rcx+1Ch], 8
0x180029a9e  jz      short loc_180029ABC
0x180029aa0  mov     rcx, [rcx+10h]
0x180029aa4  lea     r8, WPP_49d531a97551358b2c2543ad66978cd1_Traceguids
0x180029aab  mov     edx, 19h
0x180029ab0  mov     [rsp+478h+var_458], esi
0x180029ab4  mov     r9, rbp
0x180029ab7  call    WPP_SF__guid_D
0x180029abc  test    rbx, rbx
0x180029abf  jz      short loc_180029AC9
0x180029ac1  mov     rcx, rbx; lpMem
0x180029ac4  call    PAFreeTxFilter
0x180029ac9  mov     qword ptr [r15], 0
0x180029ad0  mov     eax, esi
0x180029ad2  jmp     loc_180029BA8
0x180029ad7  mov     ecx, [rdi+28h]
0x180029ada  lea     rdx, [rbx+20h]
0x180029ade  call    PASetInterfaceType
0x180029ae3  mov     ecx, [r14+28h]
0x180029ae7  lea     r8, [rbx+30h]
0x180029aeb  mov     [rbx+24h], ecx
0x180029aee  lea     rdx, [r14+2Ch]
0x180029af2  mov     ecx, [rbx]
0x180029af4  mov     [rbx+28h], esi
0x180029af7  call    PASetAddress
0x180029afc  mov     ecx, [rbx]
0x180029afe  lea     r8, [rbx+58h]
0x180029b02  lea     rdx, [r14+54h]
0x180029b06  call    PASetAddress
0x180029b0b  mov     dword ptr [rbx+80h], 1
0x180029b15  lea     r8, [rbx+9Ch]
0x180029b1c  mov     eax, [r14+8Ch]
0x180029b23  lea     rdx, [rbx+98h]
0x180029b2a  mov     [rbx+84h], eax
0x180029b30  mov     rcx, r13
0x180029b33  mov     eax, [r14+7Ch]
0x180029b37  mov     [rbx+88h], eax
0x180029b3d  movzx   eax, word ptr [r14+80h]
0x180029b45  mov     [rbx+8Ch], ax
0x180029b4c  movzx   eax, word ptr [r14+82h]
0x180029b54  mov     [rbx+8Eh], ax
0x180029b5b  mov     eax, [r14+84h]
0x180029b62  mov     [rbx+90h], eax
0x180029b68  movzx   eax, word ptr [r14+88h]
0x180029b70  mov     [rbx+94h], ax
0x180029b77  movzx   eax, word ptr [r14+8Ah]
0x180029b7f  mov     [rbx+96h], ax
0x180029b86  call    SetFilterActions
0x180029b8b  mov     qword ptr [rbx+0A0h], 0
0x180029b96  xor     eax, eax
0x180029b98  movups  xmm0, xmmword ptr [r12]
0x180029b9d  movdqu  xmmword ptr [rbx+0A8h], xmm0
0x180029ba5  mov     [r15], rbx
0x180029ba8  mov     rcx, [rsp+478h+var_48]
0x180029bb0  xor     rcx, rsp; StackCookie
0x180029bb3  call    __security_check_cookie
0x180029bb8  mov     rbx, [rsp+478h+arg_0]
0x180029bc0  add     rsp, 440h
0x180029bc7  pop     r15
0x180029bc9  pop     r14
0x180029bcb  pop     r13
0x180029bcd  pop     r12
0x180029bcf  pop     rdi
0x180029bd0  pop     rsi
0x180029bd1  pop     rbp
0x180029bd2  retn
```
