# PsmpQueryApplicationPropertiesFromExtension

- ea: `0x18001deb0`
- end: `0x18001e040`
- name: `PsmpQueryApplicationPropertiesFromExtension`
- size: `400`
- prototype: `__int64 __fastcall(PSID Sid2, char, __int64, int, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180008cc0`
- `0x180009b40`
- `0x18000a750`
- `0x18000a8d0`
- `0x180017fa0`
- `0x18001a444`
- `0x18001deb0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001dfac`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001dfac`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e00e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001e00e`

## pseudocode

```c
__int64 __fastcall PsmpQueryApplicationPropertiesFromExtension(
        PSID Sid2,
        char a2,
        __int64 a3,
        int a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  int v9; // ebx
  __int64 v10; // r15
  __int64 v11; // r12
  __int64 v12; // r13
  __int64 v13; // r9
  __int64 v15; // rsi
  __int64 *HostJobContext; // rdi
  __int64 v17; // rbp
  unsigned int ApplicationProperties; // ebx
  __int64 v19[11]; // [rsp+50h] [rbp-58h] BYREF
  __int64 v20; // [rsp+E0h] [rbp+38h]

  v19[0] = 0;
  v9 = a3;
  v10 = a7 & -(__int64)((*(_DWORD *)(a7 + 28) & 2) != 0);
  v11 = (a7 + 8) & -(__int64)((*(_DWORD *)(a7 + 28) & 4) != 0);
  v12 = (a7 + 16) & -(__int64)((*(_DWORD *)(a7 + 28) & 8) != 0);
  v20 = (a7 + 24) & -(__int64)((*(_DWORD *)(a7 + 28) & 0x10) != 0);
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(a3 + 2 * v13) );
  if ( (int)PsmpFindApplicationByManagerForUser(Sid2, a2, a3, 2 * v13 + 2, a6, v19) >= 0 )
  {
    v15 = v19[0];
    HostJobContext = 0;
    v17 = v19[0] + 328;
    RtlAcquireSRWLockExclusive(v19[0] + 328);
    if ( a4 != 4 || (HostJobContext = PsmpFindHostJobContext(v15, a5)) != 0 )
      ApplicationProperties = PsmpQueryApplicationProperties(v15, a4, a5, 0, v10, v11, v12, v20);
    else
      ApplicationProperties = -1073741772;
    RtlReleaseSRWLockExclusive(v17);
    if ( HostJobContext )
      PsmpDereferenceHostContext(HostJobContext, 0);
    PsmpDereferenceApplicationEx(v15, 0);
    return ApplicationProperties;
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        (unsigned int)&WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
        v9,
        a2);
    return 3221225524LL;
  }
}

```

## disassembly

```asm
0x18001deb0  push    rbx
0x18001deb2  push    rbp
0x18001deb3  push    rsi
0x18001deb4  push    rdi
0x18001deb5  push    r12
0x18001deb7  push    r13
0x18001deb9  push    r14
0x18001debb  push    r15
0x18001debd  sub     rsp, 68h
0x18001dec1  mov     r10, [rsp+0A8h+arg_30]
0x18001dec9  xor     ebp, ebp
0x18001decb  mov     edi, edx
0x18001decd  mov     [rsp+0A8h+var_58], rbp
0x18001ded2  mov     rsi, rcx
0x18001ded5  mov     r14d, r9d
0x18001ded8  mov     rbx, r8
0x18001dedb  mov     r11d, [r10+1Ch]
0x18001dedf  lea     rcx, [r10+10h]
0x18001dee3  mov     eax, r11d
0x18001dee6  mov     edx, r11d
0x18001dee9  and     al, 2
0x18001deeb  neg     al
0x18001deed  lea     rax, [r10+8]
0x18001def1  sbb     r15, r15
0x18001def4  and     dl, 4
0x18001def7  and     r15, r10
0x18001defa  neg     dl
0x18001defc  sbb     r12, r12
0x18001deff  and     r12, rax
0x18001df02  mov     eax, r11d
0x18001df05  and     al, 8
0x18001df07  neg     al
0x18001df09  lea     rax, [r10+18h]
0x18001df0d  sbb     r13, r13
0x18001df10  and     r11b, 10h
0x18001df14  and     r13, rcx
0x18001df17  neg     r11b
0x18001df1a  sbb     rcx, rcx
0x18001df1d  and     rcx, rax
0x18001df20  mov     [rsp+0A8h+arg_30], rcx
0x18001df28  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001df2c  inc     r9
0x18001df2f  cmp     [r8+r9*2], bp
0x18001df34  jnz     short loc_18001DF2C
0x18001df36  lea     rax, [rsp+0A8h+var_58]
0x18001df3b  mov     edx, edi
0x18001df3d  mov     [rsp+0A8h+var_80], rax; __int64
0x18001df42  lea     r9, ds:2[r9*2]
0x18001df4a  mov     eax, [rsp+0A8h+arg_28]
0x18001df51  mov     rcx, rsi; Sid2
0x18001df54  mov     [rsp+0A8h+var_88], eax; int
0x18001df58  call    PsmpFindApplicationByManagerForUser
0x18001df5d  test    eax, eax
0x18001df5f  jns     short loc_18001DF9A
0x18001df61  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df68  test    byte ptr [rcx+1Ch], 2
0x18001df6c  jz      short loc_18001DF90
0x18001df6e  cmp     byte ptr [rcx+19h], 2
0x18001df72  jb      short loc_18001DF90
0x18001df74  mov     rcx, [rcx+10h]
0x18001df78  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids
0x18001df7f  mov     edx, 30h ; '0'
0x18001df84  mov     [rsp+0A8h+var_88], edi
0x18001df88  mov     r9, rbx
0x18001df8b  call    WPP_SF_Sd
0x18001df90  mov     eax, 0C0000034h
0x18001df95  jmp     loc_18001E02F
0x18001df9a  mov     rsi, [rsp+0A8h+var_58]
0x18001df9f  mov     rdi, rbp
0x18001dfa2  lea     rbp, [rsi+148h]
0x18001dfa9  mov     rcx, rbp
0x18001dfac  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001dfb2  cmp     r14d, 4
0x18001dfb6  jnz     short loc_18001DFD7
0x18001dfb8  mov     rdx, [rsp+0A8h+arg_20]
0x18001dfc0  mov     rcx, rsi
0x18001dfc3  call    PsmpFindHostJobContext
0x18001dfc8  mov     rdi, rax
0x18001dfcb  test    rax, rax
0x18001dfce  jnz     short loc_18001DFD7
0x18001dfd0  mov     ebx, 0C0000034h
0x18001dfd5  jmp     short loc_18001E00B
0x18001dfd7  mov     rax, [rsp+0A8h+arg_30]
0x18001dfdf  xor     r9d, r9d
0x18001dfe2  mov     r8, [rsp+0A8h+arg_20]
0x18001dfea  mov     edx, r14d
0x18001dfed  mov     [rsp+0A8h+var_70], rax
0x18001dff2  mov     rcx, rsi
0x18001dff5  mov     [rsp+0A8h+var_78], r13
0x18001dffa  mov     [rsp+0A8h+var_80], r12
0x18001dfff  mov     qword ptr [rsp+0A8h+var_88], r15
0x18001e004  call    PsmpQueryApplicationProperties
0x18001e009  mov     ebx, eax
0x18001e00b  mov     rcx, rbp
0x18001e00e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001e014  test    rdi, rdi
0x18001e017  jz      short loc_18001E023
0x18001e019  xor     edx, edx
0x18001e01b  mov     rcx, rdi
0x18001e01e  call    PsmpDereferenceHostContext
0x18001e023  xor     edx, edx
0x18001e025  mov     rcx, rsi
0x18001e028  call    PsmpDereferenceApplicationEx
0x18001e02d  mov     eax, ebx
0x18001e02f  add     rsp, 68h
0x18001e033  pop     r15
0x18001e035  pop     r14
0x18001e037  pop     r13
0x18001e039  pop     r12
0x18001e03b  pop     rdi
0x18001e03c  pop     rsi
0x18001e03d  pop     rbp
0x18001e03e  pop     rbx
0x18001e03f  retn
```
