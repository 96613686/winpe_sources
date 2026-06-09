# TlsGenerateMasterKey

- ea: `0x18001355c`
- end: `0x18001373a`
- name: `TlsGenerateMasterKey`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006070`

## callees

- `0x180005cb0`
- `0x1800081a8`
- `0x18000b594`
- `0x18000b654`
- `0x18001355c`
- `0x180020248`

## string_xrefs

- `0x18001362e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180013700`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsGenerateMasterKey(__int64 a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  int v7; // r14d
  int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // r9
  int v13; // [rsp+28h] [rbp-39h]
  int v14; // [rsp+68h] [rbp+7h] BYREF
  int v15; // [rsp+6Ch] [rbp+Bh] BYREF
  _OWORD *v16; // [rsp+70h] [rbp+Fh] BYREF
  _OWORD *v17; // [rsp+78h] [rbp+17h] BYREF
  _BYTE *v18; // [rsp+80h] [rbp+1Fh] BYREF
  int v19; // [rsp+D0h] [rbp+6Fh] BYREF

  v17 = 0;
  v14 = 0;
  v16 = 0;
  v19 = 0;
  v18 = 0;
  v15 = 0;
  if ( a2 && (v7 = *(_DWORD *)a2, *(_DWORD *)a2 >= 0x10u) && a3 && *a3 >= 0x50u )
  {
    v8 = TlsParseParameterList(a4, (unsigned int)a3[2], &v17, &v14, &v16, &v19, &v18, &v15, 0, 0, 0);
    v10 = v8;
    if ( v8 >= 0 )
    {
      if ( a3[2] < 0x301u )
      {
        v8 = Ssl3ComputeMasterKey(a1, (UCHAR *)(a2 + 12), v7 - 12, (__int64)(a3 + 7), v13, v17, v14, v16, v19);
        v10 = v8;
        if ( v8 >= 0 )
          return v10;
        v11 = 1222;
      }
      else
      {
        v8 = Tls1ComputeMasterKey(v9, (__int64)a3, a2, (int)v17, v14, (__int64)v16, v19, v18, v15);
        v10 = v8;
        if ( v8 >= 0 )
          return v10;
        v11 = 1204;
      }
    }
    else
    {
      v11 = 1174;
    }
    DebugTraceError((unsigned int)v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v11);
  }
  else
  {
    v10 = -2146893779;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        45,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        129);
  }
  return v10;
}

```

## disassembly

```asm
0x18001355c  mov     r11, rsp
0x18001355f  push    rbp
0x180013560  push    rbx
0x180013561  push    rsi
0x180013562  push    rdi
0x180013563  push    r14
0x180013565  push    r15
0x180013567  lea     rbp, [r11-5Fh]
0x18001356b  sub     rsp, 88h
0x180013572  mov     [rbp+57h+var_40], 0
0x18001357a  mov     rax, r9
0x18001357d  mov     [rbp+57h+var_50], 0
0x180013584  mov     rdi, r8
0x180013587  mov     [rbp+57h+var_48], 0
0x18001358f  mov     rsi, rdx
0x180013592  mov     [rbp+57h+arg_8], 0
0x180013599  mov     r15, rcx
0x18001359c  mov     [rbp+57h+var_38], 0
0x1800135a4  mov     [rbp+57h+var_4C], 0
0x1800135ab  test    rdx, rdx
0x1800135ae  jz      loc_1800136DE
0x1800135b4  mov     r14d, [rdx]
0x1800135b7  cmp     r14d, 10h
0x1800135bb  jb      loc_1800136DE
0x1800135c1  test    r8, r8
0x1800135c4  jz      loc_1800136DE
0x1800135ca  cmp     dword ptr [r8], 50h ; 'P'
0x1800135ce  jb      loc_1800136DE
0x1800135d4  mov     edx, [rdi+8]
0x1800135d7  lea     rcx, [rbp+57h+var_4C]
0x1800135db  mov     qword ptr [r11-68h], 0
0x1800135e3  lea     r9, [rbp+57h+var_50]
0x1800135e7  mov     qword ptr [r11-70h], 0
0x1800135ef  lea     r8, [rbp+57h+var_40]
0x1800135f3  mov     qword ptr [r11-78h], 0
0x1800135fb  mov     [r11-80h], rcx
0x1800135ff  lea     rcx, [rbp+57h+var_38]
0x180013603  mov     [rsp+0B0h+var_80], rcx
0x180013608  lea     rcx, [rbp+57h+arg_8]
0x18001360c  mov     [rsp+0B0h+var_88], rcx
0x180013611  lea     rcx, [rbp+57h+var_48]
0x180013615  mov     [rsp+0B0h+var_90], rcx
0x18001361a  mov     rcx, rax
0x18001361d  call    TlsParseParameterList
0x180013622  mov     ebx, eax
0x180013624  test    eax, eax
0x180013626  jns     short loc_180013648
0x180013628  mov     r9d, 496h
0x18001362e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013635  mov     ecx, eax
0x180013637  lea     rdx, aStatus; "Status"
0x18001363e  call    DebugTraceError
0x180013643  jmp     loc_180013728
0x180013648  cmp     dword ptr [rdi+8], 301h
0x18001364f  jb      short loc_180013699
0x180013651  mov     eax, [rbp+57h+var_4C]
0x180013654  mov     r8, rsi
0x180013657  mov     r9, [rbp+57h+var_40]
0x18001365b  mov     rdx, rdi
0x18001365e  mov     [rsp+40h], eax
0x180013662  mov     rax, [rbp+57h+var_38]
0x180013666  mov     qword ptr [rsp+0B0h+var_78], rax
0x18001366b  mov     eax, [rbp+57h+arg_8]
0x18001366e  mov     dword ptr [rsp+0B0h+var_80], eax
0x180013672  mov     rax, [rbp+57h+var_48]
0x180013676  mov     [rsp+0B0h+var_88], rax
0x18001367b  mov     eax, [rbp+57h+var_50]
0x18001367e  mov     dword ptr [rsp+0B0h+var_90], eax
0x180013682  call    Tls1ComputeMasterKey
0x180013687  mov     ebx, eax
0x180013689  test    eax, eax
0x18001368b  jns     loc_180013728
0x180013691  mov     r9d, 4B4h
0x180013697  jmp     short loc_18001362E
0x180013699  mov     eax, [rbp+57h+arg_8]
0x18001369c  lea     r9, [rdi+1Ch]
0x1800136a0  mov     [rsp+40h], eax
0x1800136a4  lea     r8d, [r14-0Ch]
0x1800136a8  mov     rax, [rbp+57h+var_48]
0x1800136ac  lea     rdx, [rsi+0Ch]
0x1800136b0  mov     qword ptr [rsp+0B0h+var_78], rax
0x1800136b5  mov     rcx, r15
0x1800136b8  mov     eax, [rbp+57h+var_50]
0x1800136bb  mov     dword ptr [rsp+0B0h+var_80], eax
0x1800136bf  mov     rax, [rbp+57h+var_40]
0x1800136c3  mov     [rsp+0B0h+var_88], rax
0x1800136c8  call    Ssl3ComputeMasterKey
0x1800136cd  mov     ebx, eax
0x1800136cf  test    eax, eax
0x1800136d1  jns     short loc_180013728
0x1800136d3  mov     r9d, 4C6h
0x1800136d9  jmp     loc_18001362E
0x1800136de  mov     ebx, 8009002Dh
0x1800136e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136ea  lea     rax, WPP_GLOBAL_Control
0x1800136f1  cmp     rcx, rax
0x1800136f4  jz      short loc_180013728
0x1800136f6  test    byte ptr [rcx+1Ch], 1
0x1800136fa  jz      short loc_180013728
0x1800136fc  mov     rcx, [rcx+10h]
0x180013700  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013707  mov     dword ptr [rsp+0B0h+var_80], 481h
0x18001370f  lea     r9, aStatus; "Status"
0x180013716  mov     [rsp+0B0h+var_88], rax
0x18001371b  mov     dword ptr [rsp+0B0h+var_90], 8009002Dh
0x180013723  call    WPP_SF_sDsd
0x180013728  mov     eax, ebx
0x18001372a  add     rsp, 88h
0x180013731  pop     r15
0x180013733  pop     r14
0x180013735  pop     rdi
0x180013736  pop     rsi
0x180013737  pop     rbx
0x180013738  pop     rbp
0x180013739  retn
```
