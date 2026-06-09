# CheckPrimaryComputerRelationship(void *,bool &)

- ea: `0x18001b214`
- end: `0x18001b381`
- name: `?CheckPrimaryComputerRelationship@@YAJPEAXAEA_N@Z`
- size: `365`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015f30`

## callees

- `0x18000a8f0`
- `0x18001b214`
- `0x18001b388`
- `0x18001b5ec`
- `0x18001b7bc`
- `0x18001b8a0`
- `0x18001c64c`
- `0x18001d500`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001b2dc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001b2dc`

## pseudocode

```c
__int64 __fastcall CheckPrimaryComputerRelationship(HANDLE TokenHandle, bool *a2)
{
  unsigned __int16 **v3; // r14
  unsigned int v4; // esi
  int DomainName; // ebx
  int DomainNetBIOSName; // eax
  UstCommon::CImpersonator **v8; // rdx
  WCHAR *v9; // r13
  __int64 v10; // r9
  __int64 v11; // r15
  unsigned __int16 **v12; // r8
  __int64 v13; // rbx
  char v14; // al
  const WCHAR *v15; // r13
  unsigned __int16 **v17; // [rsp+30h] [rbp-20h] BYREF
  LPCWSTR lpString1; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 **v19; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v20; // [rsp+98h] [rbp+48h] BYREF
  unsigned int v21; // [rsp+A0h] [rbp+50h] BYREF
  unsigned __int16 *v22; // [rsp+A8h] [rbp+58h] BYREF

  v19 = 0;
  v3 = 0;
  v17 = 0;
  v4 = 0;
  v20 = 0;
  v21 = 0;
  *a2 = 0;
  v22 = 0;
  lpString1 = 0;
  DomainName = CUstComputer::GetDomainName(&v22);
  if ( DomainName >= 0 )
  {
    DomainNetBIOSName = CUstComputer::GetDomainNetBIOSName((unsigned __int16 **)&lpString1);
    v9 = (WCHAR *)lpString1;
    DomainName = DomainNetBIOSName;
    if ( DomainNetBIOSName >= 0 )
    {
      DomainName = CUstUser::GetUserAndGroupDn(TokenHandle, lpString1, &v17, &v21);
      if ( DomainName >= 0 )
      {
        DomainName = CUstComputer::GetPrimaryComputerFor(v22, &v19, &v20, v10);
        if ( DomainName < 0 || (v11 = 0, *a2) )
        {
          v3 = v19;
          v4 = v20;
        }
        else
        {
          v3 = v19;
          v4 = v20;
          do
          {
            if ( (unsigned int)v11 >= v21 )
              break;
            v12 = v17;
            v13 = 0;
            *a2 = 0;
            v14 = 0;
            v15 = v12[v11];
            do
            {
              if ( (unsigned int)v13 >= v4 )
                break;
              if ( !lstrcmpiW(v15, v3[v13]) )
                *a2 = 1;
              v14 = *a2;
              v13 = (unsigned int)(v13 + 1);
            }
            while ( !*a2 );
            DomainName = 0;
            v8 = &WPP_GLOBAL_Control;
            v9 = (WCHAR *)lpString1;
            if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                (unsigned int)&WPP_GLOBAL_Control,
                (_DWORD)v12,
                (unsigned int)v17[v11],
                v14);
            }
            v11 = (unsigned int)(v11 + 1);
          }
          while ( !*a2 );
        }
      }
    }
    if ( v9 )
      operator delete(v9, (unsigned __int64)v8);
  }
  if ( v22 )
    operator delete(v22, 2u);
  CUstUtil::ReleaseStringArray(v3, v4);
  CUstUtil::ReleaseStringArray(v17, v21);
  return (unsigned int)DomainName;
}

```

## disassembly

```asm
0x18001b214  push    rbp
0x18001b216  push    rbx
0x18001b217  push    rsi
0x18001b218  push    rdi
0x18001b219  push    r13
0x18001b21b  push    r14
0x18001b21d  push    r15
0x18001b21f  mov     rbp, rsp
0x18001b222  sub     rsp, 50h
0x18001b226  xor     eax, eax
0x18001b228  mov     r15, rcx
0x18001b22b  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x18001b22f  mov     [rbp+var_10], rax
0x18001b233  mov     r14d, eax
0x18001b236  mov     [rbp+var_20], rax
0x18001b23a  mov     esi, eax
0x18001b23c  mov     [rbp+arg_8], eax
0x18001b23f  mov     [rbp+arg_10], eax
0x18001b242  mov     rdi, rdx
0x18001b245  mov     [rdx], al
0x18001b247  mov     [rbp+arg_18], rax
0x18001b24b  mov     [rbp+lpString1], rax
0x18001b24f  call    ?GetDomainName@CUstComputer@@SAJPEAPEAG@Z; CUstComputer::GetDomainName(ushort * *)
0x18001b254  mov     ebx, eax
0x18001b256  test    eax, eax
0x18001b258  js      loc_18001B345
0x18001b25e  lea     rcx, [rbp+lpString1]; unsigned __int16 **
0x18001b262  call    ?GetDomainNetBIOSName@CUstComputer@@SAJPEAPEAG@Z; CUstComputer::GetDomainNetBIOSName(ushort * *)
0x18001b267  mov     r13, [rbp+lpString1]
0x18001b26b  mov     ebx, eax
0x18001b26d  test    eax, eax
0x18001b26f  js      loc_18001B338
0x18001b275  lea     r9, [rbp+arg_10]; unsigned int *
0x18001b279  mov     rdx, r13; lpString1
0x18001b27c  lea     r8, [rbp+var_20]; unsigned __int16 ***
0x18001b280  mov     rcx, r15; TokenHandle
0x18001b283  call    ?GetUserAndGroupDn@CUstUser@@SAJPEAXPEAGQEAPEAPEAGAEAK@Z; CUstUser::GetUserAndGroupDn(void *,ushort *,ushort * * * const,ulong &)
0x18001b288  mov     ebx, eax
0x18001b28a  test    eax, eax
0x18001b28c  js      loc_18001B338
0x18001b292  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x18001b296  lea     r8, [rbp+arg_8]; unsigned int *
0x18001b29a  lea     rdx, [rbp+var_10]; unsigned __int16 ***
0x18001b29e  call    ?GetPrimaryComputerFor@CUstComputer@@SAJPEAGPEAPEAPEAGAEAK@Z; CUstComputer::GetPrimaryComputerFor(ushort *,ushort * * *,ulong &)
0x18001b2a3  mov     ebx, eax
0x18001b2a5  test    eax, eax
0x18001b2a7  js      loc_18001B331
0x18001b2ad  xor     r15d, r15d
0x18001b2b0  cmp     [rdi], sil
0x18001b2b3  jnz     short loc_18001B331
0x18001b2b5  mov     r14, [rbp+var_10]
0x18001b2b9  mov     esi, [rbp+arg_8]
0x18001b2bc  cmp     r15d, [rbp+arg_10]
0x18001b2c0  jnb     short loc_18001B338
0x18001b2c2  mov     r8, [rbp+var_20]
0x18001b2c6  xor     ebx, ebx
0x18001b2c8  mov     byte ptr [rdi], 0
0x18001b2cb  xor     al, al
0x18001b2cd  mov     r13, [r8+r15*8]
0x18001b2d1  cmp     ebx, esi
0x18001b2d3  jnb     short loc_18001B2F1
0x18001b2d5  mov     rdx, [r14+rbx*8]; lpString2
0x18001b2d9  mov     rcx, r13; lpString1
0x18001b2dc  call    cs:__imp_lstrcmpiW
0x18001b2e2  test    eax, eax
0x18001b2e4  jnz     short loc_18001B2E9
0x18001b2e6  mov     byte ptr [rdi], 1
0x18001b2e9  mov     al, [rdi]
0x18001b2eb  inc     ebx
0x18001b2ed  test    al, al
0x18001b2ef  jz      short loc_18001B2D1
0x18001b2f1  xor     ebx, ebx
0x18001b2f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2fa  lea     rdx, WPP_GLOBAL_Control
0x18001b301  mov     r13, [rbp+lpString1]
0x18001b305  cmp     rcx, rdx
0x18001b308  jz      short loc_18001B328
0x18001b30a  test    byte ptr [rcx+1Ch], 2
0x18001b30e  jz      short loc_18001B328
0x18001b310  mov     rcx, [rcx+10h]
0x18001b314  movzx   eax, al
0x18001b317  mov     [rsp+50h+var_30], eax
0x18001b31b  mov     rax, [rbp+var_20]
0x18001b31f  mov     r9, [rax+r15*8]
0x18001b323  call    WPP_SF_Sd
0x18001b328  inc     r15d
0x18001b32b  cmp     [rdi], bl
0x18001b32d  jz      short loc_18001B2BC
0x18001b32f  jmp     short loc_18001B338
0x18001b331  mov     r14, [rbp+var_10]
0x18001b335  mov     esi, [rbp+arg_8]
0x18001b338  test    r13, r13
0x18001b33b  jz      short loc_18001B345
0x18001b33d  mov     rcx, r13; void *
0x18001b340  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b345  cmp     [rbp+arg_18], 0
0x18001b34a  jz      short loc_18001B35A
0x18001b34c  mov     rcx, [rbp+arg_18]; void *
0x18001b350  mov     edx, 2; unsigned __int64
0x18001b355  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b35a  mov     edx, esi; unsigned int
0x18001b35c  mov     rcx, r14; unsigned __int16 **
0x18001b35f  call    ?ReleaseStringArray@CUstUtil@@SAXQEAPEAGK@Z; CUstUtil::ReleaseStringArray(ushort * * const,ulong)
0x18001b364  mov     edx, [rbp+arg_10]; unsigned int
0x18001b367  mov     rcx, [rbp+var_20]; unsigned __int16 **
0x18001b36b  call    ?ReleaseStringArray@CUstUtil@@SAXQEAPEAGK@Z; CUstUtil::ReleaseStringArray(ushort * * const,ulong)
0x18001b370  mov     eax, ebx
0x18001b372  add     rsp, 50h
0x18001b376  pop     r15
0x18001b378  pop     r14
0x18001b37a  pop     r13
0x18001b37c  pop     rdi
0x18001b37d  pop     rsi
0x18001b37e  pop     rbx
0x18001b37f  pop     rbp
0x18001b380  retn
```
