# BITSCreateFile2(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x18006b0c0`
- end: `0x18006b290`
- name: `?BITSCreateFile2@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `464`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, void *TokenInformation)`
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028d60`
- `0x1800507a0`
- `0x18008b230`
- `0x180096bc4`
- `0x1800ecbf0`
- `0x1800ed0a0`

## callees

- `0x18006b0c0`
- `0x18009e9c8`
- `0x1800ab738`
- `0x1800f5574`
- `0x1800f5798`
- `0x1800f5d60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b253`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b253`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006b156`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006b156`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18006b232`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18006b232`

## string_xrefs

- `0x18006b228`: `CreateFile2`
- `0x18006b205`: `BITSCreateFile2AsApp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall BITSCreateFile2(
        const unsigned __int16 *a1,
        unsigned int a2,
        unsigned int a3,
        struct _SECURITY_ATTRIBUTES *a4,
        unsigned int a5,
        unsigned int a6,
        void *TokenInformation)
{
  DWORD v11; // eax
  const wchar_t *v13; // rdi
  void *File2; // rax
  void *v15; // rbx
  char LastError; // al
  DWORD ReturnLength; // [rsp+40h] [rbp-78h] BYREF
  _DWORD v18[3]; // [rsp+48h] [rbp-70h] BYREF
  unsigned int v19; // [rsp+54h] [rbp-64h]
  struct _SECURITY_ATTRIBUTES *v20; // [rsp+58h] [rbp-60h]
  __int64 v21; // [rsp+60h] [rbp-58h]

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SDDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (_DWORD)a1, a2, a3, a5, a6);
  ReturnLength = 0;
  LODWORD(TokenInformation) = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    v19 = 0;
    v18[0] = 32;
    v18[1] = a6 & 0x7FB7;
    v20 = a4;
    v18[2] = a6 & 0xFFF00000;
    v21 = 0;
    if ( (a6 & 0x100000) != 0 )
      v19 = a6 & 0x1F0000;
    if ( (_DWORD)TokenInformation && IsAppContainerFileFunctionalitySupported() )
    {
      v13 = L"BITSCreateFile2AsApp";
      File2 = BITSCreateFile2AsApp(a1, a2, a3, a5, (struct _CREATEFILE2_EXTENDED_PARAMETERS *)v18);
    }
    else
    {
      v13 = L"CreateFile2";
      File2 = (void *)CreateFile2(a1, a2, a3, a5, v18);
    }
    v15 = File2;
    if ( File2 == (void *)-1LL
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids,
        (_DWORD)v13,
        LastError);
    }
    return (__int64)v15;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v11 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids, v11);
    }
    return -1;
  }
}

```

## disassembly

```asm
0x18006b0c0  push    rbx
0x18006b0c2  push    rbp
0x18006b0c3  push    rsi
0x18006b0c4  push    rdi
0x18006b0c5  push    r12
0x18006b0c7  push    r13
0x18006b0c9  push    r14
0x18006b0cb  push    r15
0x18006b0cd  sub     rsp, 78h
0x18006b0d1  mov     rdi, r9
0x18006b0d4  mov     esi, r8d
0x18006b0d7  mov     ebp, edx
0x18006b0d9  mov     r14, rcx
0x18006b0dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b0e3  lea     r13, WPP_GLOBAL_Control
0x18006b0ea  mov     ebx, [rsp+0B8h+arg_28]
0x18006b0f1  mov     r15d, [rsp+0B8h+arg_20]
0x18006b0f9  cmp     rcx, r13
0x18006b0fc  jz      short loc_18006B122
0x18006b0fe  test    byte ptr [rcx+1Ch], 1
0x18006b102  jz      short loc_18006B122
0x18006b104  mov     rcx, [rcx+10h]
0x18006b108  mov     r9, r14
0x18006b10b  mov     [rsp+0B8h+var_80], ebx
0x18006b10f  mov     [rsp+0B8h+var_88], r15d
0x18006b114  mov     [rsp+0B8h+var_90], r8d
0x18006b119  mov     dword ptr [rsp+0B8h+ReturnLength], edx
0x18006b11d  call    WPP_SF_SDDDD
0x18006b122  xor     r12d, r12d
0x18006b125  lea     rax, [rsp+0B8h+var_78]
0x18006b12a  mov     r9d, 4; TokenInformationLength
0x18006b130  mov     [rsp+0B8h+var_78], r12d
0x18006b135  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18006b13d  mov     dword ptr [rsp+0B8h+TokenInformation], r12d
0x18006b145  mov     edx, 1Dh; TokenInformationClass
0x18006b14a  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18006b14f  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18006b156  call    cs:__imp_GetTokenInformation
0x18006b15c  test    eax, eax
0x18006b15e  jnz     short loc_18006B1A3
0x18006b160  mov     rax, cs:WPP_GLOBAL_Control
0x18006b167  cmp     rax, r13
0x18006b16a  jz      short loc_18006B197
0x18006b16c  test    byte ptr [rax+1Ch], 4
0x18006b170  jz      short loc_18006B197
0x18006b172  call    cs:__imp_GetLastError
0x18006b178  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b17f  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x18006b186  mov     edx, 28h ; '('
0x18006b18b  mov     r9d, eax
0x18006b18e  mov     rcx, [rcx+10h]
0x18006b192  call    WPP_SF_d
0x18006b197  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18006b19e  jmp     loc_18006B27F
0x18006b1a3  mov     eax, ebx
0x18006b1a5  mov     [rsp+0B8h+var_64], r12d
0x18006b1aa  and     eax, 7FB7h
0x18006b1af  mov     [rsp+0B8h+var_70], 20h ; ' '
0x18006b1b7  mov     [rsp+0B8h+var_6C], eax
0x18006b1bb  mov     eax, ebx
0x18006b1bd  and     eax, 0FFF00000h
0x18006b1c2  mov     [rsp+0B8h+var_60], rdi
0x18006b1c7  mov     [rsp+0B8h+var_68], eax
0x18006b1cb  mov     [rsp+0B8h+var_58], r12
0x18006b1d0  bt      ebx, 14h
0x18006b1d4  jnb     short loc_18006B1E0
0x18006b1d6  and     ebx, 1F0000h
0x18006b1dc  mov     [rsp+0B8h+var_64], ebx
0x18006b1e0  cmp     dword ptr [rsp+0B8h+TokenInformation], r12d
0x18006b1e8  jz      short loc_18006B216
0x18006b1ea  call    ?IsAppContainerFileFunctionalitySupported@@YA_NXZ; IsAppContainerFileFunctionalitySupported(void)
0x18006b1ef  test    al, al
0x18006b1f1  jz      short loc_18006B216
0x18006b1f3  lea     rax, [rsp+0B8h+var_70]
0x18006b1f8  mov     r9d, r15d; unsigned int
0x18006b1fb  mov     r8d, esi; unsigned int
0x18006b1fe  mov     [rsp+0B8h+ReturnLength], rax; struct _CREATEFILE2_EXTENDED_PARAMETERS *
0x18006b203  mov     edx, ebp; unsigned int
0x18006b205  lea     rdi, aBitscreatefile; "BITSCreateFile2AsApp"
0x18006b20c  mov     rcx, r14; unsigned __int16 *
0x18006b20f  call    ?BITSCreateFile2AsApp@@YAPEAXPEBGKKKPEAU_CREATEFILE2_EXTENDED_PARAMETERS@@@Z; BITSCreateFile2AsApp(ushort const *,ulong,ulong,ulong,_CREATEFILE2_EXTENDED_PARAMETERS *)
0x18006b214  jmp     short loc_18006B238
0x18006b216  lea     rax, [rsp+0B8h+var_70]
0x18006b21b  mov     r9d, r15d
0x18006b21e  mov     r8d, esi
0x18006b221  mov     [rsp+0B8h+ReturnLength], rax
0x18006b226  mov     edx, ebp
0x18006b228  lea     rdi, aCreatefile2; "CreateFile2"
0x18006b22f  mov     rcx, r14
0x18006b232  call    cs:__imp_CreateFile2
0x18006b238  mov     rbx, rax
0x18006b23b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006b23f  jnz     short loc_18006B27C
0x18006b241  mov     rax, cs:WPP_GLOBAL_Control
0x18006b248  cmp     rax, r13
0x18006b24b  jz      short loc_18006B27C
0x18006b24d  test    byte ptr [rax+1Ch], 2
0x18006b251  jz      short loc_18006B27C
0x18006b253  call    cs:__imp_GetLastError
0x18006b259  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b260  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x18006b267  mov     edx, 29h ; ')'
0x18006b26c  mov     dword ptr [rsp+0B8h+ReturnLength], eax
0x18006b270  mov     r9, rdi
0x18006b273  mov     rcx, [rcx+10h]
0x18006b277  call    WPP_SF_Sd
0x18006b27c  mov     rax, rbx
0x18006b27f  add     rsp, 78h
0x18006b283  pop     r15
0x18006b285  pop     r14
0x18006b287  pop     r13
0x18006b289  pop     r12
0x18006b28b  pop     rdi
0x18006b28c  pop     rsi
0x18006b28d  pop     rbp
0x18006b28e  pop     rbx
0x18006b28f  retn
```
