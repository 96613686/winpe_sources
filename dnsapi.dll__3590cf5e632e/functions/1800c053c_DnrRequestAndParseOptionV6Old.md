# DnrRequestAndParseOptionV6Old

- ea: `0x1800c053c`
- end: `0x1800c06bb`
- name: `DnrRequestAndParseOptionV6Old`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180038688`

## callees

- `0x18008b5f0`
- `0x1800c0000`
- `0x1800c01cc`
- `0x1800c053c`

## import_xrefs

- `dhcpcsvc6!Dhcpv6RequestCachedParams` at `0x1800c062f`
- `dhcpcsvc6!Dhcpv6RequestCachedParams` at `0x1800c062f`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsDataEx` at `0x1800c0672`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsDataEx` at `0x1800c0672`
- `dhcpcsvc6!Dhcpv6RequestCachedParamsEx` at `0x1800c05e7`
- `dhcpcsvc6!Dhcpv6RequestCachedParamsEx` at `0x1800c05e7`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsData` at `0x1800c068d`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsData` at `0x1800c068d`

## pseudocode

```c
__int64 __fastcall DnrRequestAndParseOptionV6Old(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int128 v11; // [rsp+30h] [rbp-19h] BYREF
  unsigned int *v12; // [rsp+40h] [rbp-9h] BYREF
  __int128 v13; // [rsp+50h] [rbp+7h] BYREF
  __int128 v14; // [rsp+60h] [rbp+17h] BYREF
  __int128 v15; // [rsp+70h] [rbp+27h]

  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a1 || !a2 || !a3 )
  {
    v5 = 87;
    goto LABEL_21;
  }
  DWORD1(v14) = 144;
  *((_QWORD *)&v13 + 1) = &v14;
  LODWORD(v13) = 1;
  v6 = a1 + 104;
  if ( g_fVelocityDhcpv6MultiRecordOptionSupport )
  {
    v5 = Dhcpv6RequestCachedParamsEx(1, v6, 0, &v13, &v12);
    if ( v5 )
      goto LABEL_21;
    if ( v12 )
    {
      v7 = *((_QWORD *)v12 + 1);
      if ( v7 )
      {
        v8 = *v12;
        if ( (_DWORD)v8 )
        {
          v9 = DnrParseOptionV6(v7, v8, a2, a3);
LABEL_19:
          v5 = v9;
          goto LABEL_21;
        }
      }
    }
  }
  else
  {
    v11 = v13;
    v5 = Dhcpv6RequestCachedParams(0, v6, 0, &v11);
    if ( v5 )
      goto LABEL_21;
    if ( (_QWORD)v15 && DWORD2(v15) )
    {
      v9 = DnrParseOptionV6_Old(v15, DWORD2(v15), a2, a3);
      goto LABEL_19;
    }
  }
  v5 = 1168;
LABEL_21:
  if ( g_fVelocityDhcpv6MultiRecordOptionSupport )
  {
    Dhcpv6FreeCachedParamsDataEx(v12);
  }
  else
  {
    v11 = v13;
    Dhcpv6FreeCachedParamsData(&v11);
  }
  return v5;
}

```

## disassembly

```asm
0x1800c053c  mov     [rsp-8+arg_18], rbx
0x1800c0541  push    rbp
0x1800c0542  push    rsi
0x1800c0543  push    rdi
0x1800c0544  lea     rbp, [rsp-47h]
0x1800c0549  sub     rsp, 90h
0x1800c0550  mov     rax, cs:__security_cookie
0x1800c0557  xor     rax, rsp
0x1800c055a  mov     [rbp+57h+var_20], rax
0x1800c055e  mov     [rbp+57h+var_60], 0
0x1800c0566  xorps   xmm1, xmm1
0x1800c0569  xorps   xmm0, xmm0
0x1800c056c  mov     rdi, r8
0x1800c056f  mov     rsi, rdx
0x1800c0572  movups  [rbp+57h+var_50], xmm0
0x1800c0576  movups  [rbp+57h+var_40], xmm1
0x1800c057a  movups  [rbp+57h+var_30], xmm1
0x1800c057e  test    rdx, rdx
0x1800c0581  jz      short loc_1800C0589
0x1800c0583  mov     dword ptr [rdx], 0
0x1800c0589  test    rdi, rdi
0x1800c058c  jz      short loc_1800C0595
0x1800c058e  mov     qword ptr [r8], 0
0x1800c0595  test    rcx, rcx
0x1800c0598  jnz     short loc_1800C05A4
0x1800c059a  mov     ebx, 57h ; 'W'
0x1800c059f  jmp     loc_1800C0665
0x1800c05a4  test    rsi, rsi
0x1800c05a7  jz      short loc_1800C059A
0x1800c05a9  test    rdi, rdi
0x1800c05ac  jz      short loc_1800C059A
0x1800c05ae  xor     r8d, r8d
0x1800c05b1  mov     dword ptr [rbp+57h+var_40+4], 90h
0x1800c05b8  cmp     cs:g_fVelocityDhcpv6MultiRecordOptionSupport, r8d
0x1800c05bf  lea     rax, [rbp+57h+var_40]
0x1800c05c3  mov     r10d, 1
0x1800c05c9  mov     qword ptr [rbp+57h+var_50+8], rax
0x1800c05cd  mov     dword ptr [rbp+57h+var_50], r10d
0x1800c05d1  lea     rdx, [rcx+68h]
0x1800c05d5  jz      short loc_1800C0620
0x1800c05d7  lea     rax, [rbp+57h+var_60]
0x1800c05db  mov     ecx, r10d
0x1800c05de  lea     r9, [rbp+57h+var_50]
0x1800c05e2  mov     [rsp+0A0h+var_80], rax
0x1800c05e7  call    cs:__imp_Dhcpv6RequestCachedParamsEx
0x1800c05ee  nop     dword ptr [rax+rax+00h]
0x1800c05f3  mov     ebx, eax
0x1800c05f5  test    eax, eax
0x1800c05f7  jnz     short loc_1800C0665
0x1800c05f9  cmp     [rbp+57h+var_60], 0
0x1800c05fe  jz      short loc_1800C0660
0x1800c0600  mov     rax, [rbp+57h+var_60]
0x1800c0604  mov     rcx, [rax+8]
0x1800c0608  test    rcx, rcx
0x1800c060b  jz      short loc_1800C0660
0x1800c060d  mov     edx, [rax]
0x1800c060f  test    edx, edx
0x1800c0611  jz      short loc_1800C0660
0x1800c0613  mov     r9, rdi
0x1800c0616  mov     r8, rsi
0x1800c0619  call    DnrParseOptionV6
0x1800c061e  jmp     short loc_1800C065C
0x1800c0620  movaps  xmm0, [rbp+57h+var_50]
0x1800c0624  lea     r9, [rbp+57h+var_70]
0x1800c0628  xor     ecx, ecx
0x1800c062a  movdqa  [rbp+57h+var_70], xmm0
0x1800c062f  call    cs:__imp_Dhcpv6RequestCachedParams
0x1800c0636  nop     dword ptr [rax+rax+00h]
0x1800c063b  mov     ebx, eax
0x1800c063d  test    eax, eax
0x1800c063f  jnz     short loc_1800C0665
0x1800c0641  mov     rcx, qword ptr [rbp+57h+var_30]
0x1800c0645  test    rcx, rcx
0x1800c0648  jz      short loc_1800C0660
0x1800c064a  mov     edx, dword ptr [rbp+57h+var_30+8]
0x1800c064d  test    edx, edx
0x1800c064f  jz      short loc_1800C0660
0x1800c0651  mov     r9, rdi
0x1800c0654  mov     r8, rsi
0x1800c0657  call    DnrParseOptionV6_Old
0x1800c065c  mov     ebx, eax
0x1800c065e  jmp     short loc_1800C0665
0x1800c0660  mov     ebx, 490h
0x1800c0665  cmp     cs:g_fVelocityDhcpv6MultiRecordOptionSupport, 0
0x1800c066c  jz      short loc_1800C0680
0x1800c066e  mov     rcx, [rbp+57h+var_60]
0x1800c0672  call    cs:__imp_Dhcpv6FreeCachedParamsDataEx
0x1800c0679  nop     dword ptr [rax+rax+00h]
0x1800c067e  jmp     short loc_1800C0699
0x1800c0680  movaps  xmm0, [rbp+57h+var_50]
0x1800c0684  lea     rcx, [rbp+57h+var_70]
0x1800c0688  movdqa  [rbp+57h+var_70], xmm0
0x1800c068d  call    cs:__imp_Dhcpv6FreeCachedParamsData
0x1800c0694  nop     dword ptr [rax+rax+00h]
0x1800c0699  mov     eax, ebx
0x1800c069b  mov     rcx, [rbp+57h+var_20]
0x1800c069f  xor     rcx, rsp; StackCookie
0x1800c06a2  call    __security_check_cookie
0x1800c06a7  mov     rbx, [rsp+0A0h+arg_18]
0x1800c06af  add     rsp, 90h
0x1800c06b6  pop     rdi
0x1800c06b7  pop     rsi
0x1800c06b8  pop     rbp
0x1800c06b9  retn
```
