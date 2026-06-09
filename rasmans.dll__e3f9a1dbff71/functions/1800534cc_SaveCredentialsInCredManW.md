# SaveCredentialsInCredManW

- ea: `0x1800534cc`
- end: `0x18005396b`
- name: `SaveCredentialsInCredManW`
- size: `1183`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180052c00`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000e564`
- `0x180039a50`
- `0x1800534cc`
- `0x1800e7206`

## import_xrefs

- `msvcrt!wcspbrk` at `0x18005363f`
- `msvcrt!wcspbrk` at `0x18005363f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005386b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005386b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005359e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005359e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800537e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800537f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800538b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005390f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005391c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800537e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800537f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800538b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005390f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005391c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800537ba`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x1800537ba`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180053844`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180053855`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180053844`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180053855`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180053861`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180053861`

## pseudocode

```c
__int64 __fastcall SaveCredentialsInCredManW(__int64 a1, _DWORD *a2)
{
  struct _LIST_ENTRY *v4; // rbx
  bool v5; // zf
  DWORD LastError; // esi
  __int64 v7; // rdx
  __int64 v8; // r9
  unsigned __int16 *v9; // r15
  DWORD v10; // eax
  __int64 v11; // rcx
  _CREDENTIALW *p_Credential; // rax
  _WORD *v13; // rbx
  unsigned __int16 *v14; // rsi
  __int64 v15; // r9
  struct _LIST_ENTRY *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rcx
  __int64 v22; // rcx
  _BYTE *v23; // rax
  __int64 v24; // rcx
  _BYTE *v25; // rax
  DATA_BLOB pDataIn; // [rsp+30h] [rbp-49h] BYREF
  _CREDENTIALW Credential; // [rsp+40h] [rbp-39h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 130, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  memset_0(&Credential, 0, sizeof(Credential));
  v5 = (*(_BYTE *)a1 & 0x16) == 0;
  LODWORD(pDataIn.pbData) = 0;
  *(_QWORD *)&pDataIn.cbData = 0;
  if ( v5 )
  {
    LastError = 50;
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v4[1].Blink) & 0x2000) != 0
      && BYTE1(v4[1].Blink) >= 2u )
    {
      v7 = 131;
      v8 = 50;
LABEL_10:
      WPP_SF_d(v4[1].Flink, v7, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v8);
LABEL_59:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_60;
    }
    goto LABEL_60;
  }
  v9 = (unsigned __int16 *)LocalAlloc(0x40u, 0x200u);
  if ( v9 )
  {
    v11 = 80;
    p_Credential = &Credential;
    do
    {
      LOBYTE(p_Credential->Flags) = 0;
      p_Credential = (_CREDENTIALW *)((char *)p_Credential + 1);
      --v11;
    }
    while ( v11 );
    v13 = (_WORD *)(a1 + 2568);
    if ( (*(_BYTE *)a1 & 4) != 0 )
    {
      Credential.Type = 2;
    }
    else
    {
      *v13 = 0;
      Credential.Type = 3;
    }
    v14 = (unsigned __int16 *)(a1 + 2056);
    if ( !*v13 || wcspbrk((const wchar_t *)(a1 + 2056), L"@\\") )
    {
      v18 = 2147483646;
      v19 = 256;
      v20 = v9;
      do
      {
        if ( !v18 )
          break;
        if ( !*v14 )
          break;
        *v20++ = *v14++;
        --v18;
        --v19;
      }
      while ( v19 );
      v21 = v20 - 1;
      if ( v19 )
        v21 = v20;
      *v21 = 0;
      if ( !v19 )
      {
        v15 = 122;
        LastError = 122;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_58;
        }
        v17 = 134;
        goto LABEL_57;
      }
    }
    else if ( (unsigned int)StringCchPrintfW(v9, 0x100u, L"%s\\%s", a1 + 2568, a1 + 2056) )
    {
      v15 = 122;
      LastError = 122;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_58;
      }
      v17 = 133;
      goto LABEL_57;
    }
    LastError = 0;
    if ( *(_DWORD *)(a1 + 4) )
    {
      pDataIn.cbData = *(_DWORD *)(a1 + 4);
      pDataIn.pbData = (BYTE *)(a1 + 8);
      LastError = DecodeData(&pDataIn);
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 135, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, LastError);
        }
        goto LABEL_58;
      }
      if ( MEMORY[0] == 80 && RtlCompareMemory(L"_$_5bb789f2-9e37-401b-965e-e4de9804aca1", MEMORY[8], 0x50u) == 80 )
      {
        Credential.Flags |= 0x80u;
        v22 = MEMORY[0];
        v23 = (_BYTE *)MEMORY[8];
        if ( MEMORY[0] )
        {
          do
          {
            *v23++ = 0;
            --v22;
          }
          while ( v22 );
        }
        LocalFree(MEMORY[8]);
        MEMORY[8] = 0;
        LocalFree(0);
        *a2 = 1;
      }
    }
    Credential.UserName = v9;
    Credential.CredentialBlobSize = 0;
    Credential.CredentialBlob = 0;
    Credential.Persist = 1;
    Credential.TargetName = (LPWSTR)L"*Session";
    CredDeleteW(L"*Session", 3u, 0);
    CredDeleteW(Credential.TargetName, 2u, 0);
    if ( CredWriteW(&Credential, 0)
      || (LastError = GetLastError(),
          v16 = WPP_GLOBAL_Control,
          WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control)
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
LABEL_58:
      LocalFree(v9);
      goto LABEL_59;
    }
    v17 = 136;
    v15 = LastError;
LABEL_57:
    WPP_SF_d(v16[1].Flink, v17, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v15);
    goto LABEL_58;
  }
  v10 = GetLastError();
  LastError = v10;
  if ( !v10 )
    goto LABEL_59;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v7 = 132;
    v8 = v10;
    goto LABEL_10;
  }
LABEL_60:
  if ( *(_DWORD *)(a1 + 4) )
  {
    v24 = 2048;
    v25 = (_BYTE *)(a1 + 8);
    do
    {
      *v25++ = 0;
      --v24;
    }
    while ( v24 );
    *(_DWORD *)(a1 + 4) = 0;
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v4[1].Blink) & 0x2000) != 0
    && BYTE1(v4[1].Blink) >= 6u )
  {
    WPP_SF_d(v4[1].Flink, 137, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800534cc  push    rbp
0x1800534ce  push    rbx
0x1800534cf  push    rsi
0x1800534d0  push    rdi
0x1800534d1  push    r12
0x1800534d3  push    r13
0x1800534d5  push    r14
0x1800534d7  push    r15
0x1800534d9  lea     rbp, [rsp-1Fh]
0x1800534de  sub     rsp, 98h
0x1800534e5  mov     r12, rdx
0x1800534e8  mov     r14, rcx
0x1800534eb  mov     rbx, cs:WPP_GLOBAL_Control
0x1800534f2  lea     r15, WPP_GLOBAL_Control
0x1800534f9  cmp     rbx, r15
0x1800534fc  jz      short loc_180053529
0x1800534fe  test    dword ptr [rbx+1Ch], 2000h
0x180053505  jz      short loc_180053529
0x180053507  cmp     byte ptr [rbx+19h], 6
0x18005350b  jb      short loc_180053529
0x18005350d  mov     rcx, [rbx+10h]
0x180053511  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180053518  mov     edx, 82h
0x18005351d  call    WPP_SF_
0x180053522  mov     rbx, cs:WPP_GLOBAL_Control
0x180053529  mov     esi, 50h ; 'P'
0x18005352e  lea     rcx, [rbp+57h+Credential]; void *
0x180053532  mov     r8d, esi; Size
0x180053535  xor     edx, edx; Val
0x180053537  call    memset_0
0x18005353c  xor     eax, eax
0x18005353e  xor     r13d, r13d
0x180053541  test    byte ptr [r14], 16h
0x180053545  mov     edi, r13d
0x180053548  mov     qword ptr [rbp+57h+pDataIn+4], rax
0x18005354c  mov     [rbp-49h], rax
0x180053550  mov     [rbp+57h+hMem], r13
0x180053554  jnz     short loc_180053594
0x180053556  lea     esi, [rax+32h]
0x180053559  cmp     rbx, r15
0x18005355c  jz      loc_1800538C4
0x180053562  test    dword ptr [rbx+1Ch], 2000h
0x180053569  jz      loc_1800538C4
0x18005356f  cmp     byte ptr [rbx+19h], 2
0x180053573  jb      loc_1800538C4
0x180053579  lea     edx, [rsi+51h]
0x18005357c  mov     r9d, esi
0x18005357f  mov     rcx, [rbx+10h]
0x180053583  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x18005358a  call    WPP_SF_d
0x18005358f  jmp     loc_1800538BD
0x180053594  mov     edx, 200h; uBytes
0x180053599  mov     ecx, 40h ; '@'; uFlags
0x18005359e  call    cs:__imp_LocalAlloc
0x1800535a4  mov     r15, rax
0x1800535a7  test    rax, rax
0x1800535aa  jnz     short loc_1800535F4
0x1800535ac  call    cs:__imp_GetLastError
0x1800535b2  mov     esi, eax
0x1800535b4  test    eax, eax
0x1800535b6  jz      loc_1800538B6
0x1800535bc  mov     rbx, cs:WPP_GLOBAL_Control
0x1800535c3  lea     r15, WPP_GLOBAL_Control
0x1800535ca  cmp     rbx, r15
0x1800535cd  jz      loc_1800538C4
0x1800535d3  test    dword ptr [rbx+1Ch], 2000h
0x1800535da  jz      loc_1800538C4
0x1800535e0  cmp     byte ptr [rbx+19h], 2
0x1800535e4  jb      loc_1800538C4
0x1800535ea  mov     edx, 84h
0x1800535ef  mov     r9d, eax
0x1800535f2  jmp     short loc_18005357F
0x1800535f4  mov     rcx, rsi
0x1800535f7  lea     rax, [rbp+57h+Credential]
0x1800535fb  mov     [rax], r13b
0x1800535fe  inc     rax
0x180053601  sub     rcx, 1
0x180053605  jnz     short loc_1800535FB
0x180053607  test    byte ptr [r14], 4
0x18005360b  lea     rbx, [r14+0A08h]
0x180053612  jz      short loc_18005361D
0x180053614  mov     [rbp+57h+Credential.Type], 2
0x18005361b  jmp     short loc_180053628
0x18005361d  mov     [rbx], r13w
0x180053621  mov     [rbp+57h+Credential.Type], 3
0x180053628  lea     rsi, [r14+808h]
0x18005362f  cmp     r13w, [rbx]
0x180053633  jz      short loc_1800536AE
0x180053635  lea     rdx, asc_1800F113C; "@\\"
0x18005363c  mov     rcx, rsi; String
0x18005363f  call    cs:__imp_wcspbrk
0x180053645  test    rax, rax
0x180053648  jnz     short loc_1800536AE
0x18005364a  mov     r9, rbx
0x18005364d  mov     [rsp+0D0h+var_B0], rsi
0x180053652  lea     r8, aSS_2; "%s\\%s"
0x180053659  mov     edx, 100h; unsigned __int64
0x18005365e  mov     rcx, r15; unsigned __int16 *
0x180053661  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180053666  test    eax, eax
0x180053668  jz      loc_180053730
0x18005366e  mov     r9d, 7Ah ; 'z'
0x180053674  mov     esi, r9d
0x180053677  mov     rcx, cs:WPP_GLOBAL_Control
0x18005367e  lea     rax, WPP_GLOBAL_Control
0x180053685  cmp     rcx, rax
0x180053688  jz      loc_1800538AD
0x18005368e  test    dword ptr [rcx+1Ch], 2000h
0x180053695  jz      loc_1800538AD
0x18005369b  cmp     byte ptr [rcx+19h], 2
0x18005369f  jb      loc_1800538AD
0x1800536a5  lea     edx, [r9+0Bh]
0x1800536a9  jmp     loc_18005389D
0x1800536ae  mov     ecx, 7FFFFFFEh
0x1800536b3  mov     edx, 100h
0x1800536b8  mov     rax, r15
0x1800536bb  test    rcx, rcx
0x1800536be  jz      short loc_1800536DF
0x1800536c0  movzx   r8d, word ptr [rsi]
0x1800536c4  test    r8w, r8w
0x1800536c8  jz      short loc_1800536DF
0x1800536ca  mov     [rax], r8w
0x1800536ce  add     rsi, 2
0x1800536d2  add     rax, 2
0x1800536d6  dec     rcx
0x1800536d9  sub     rdx, 1
0x1800536dd  jnz     short loc_1800536BB
0x1800536df  test    rdx, rdx
0x1800536e2  lea     rcx, [rax-2]
0x1800536e6  cmovnz  rcx, rax
0x1800536ea  mov     [rcx], r13w
0x1800536ee  jnz     short loc_180053730
0x1800536f0  mov     r9d, 7Ah ; 'z'
0x1800536f6  mov     esi, r9d
0x1800536f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180053700  lea     rax, WPP_GLOBAL_Control
0x180053707  cmp     rcx, rax
0x18005370a  jz      loc_1800538AD
0x180053710  test    dword ptr [rcx+1Ch], 2000h
0x180053717  jz      loc_1800538AD
0x18005371d  cmp     byte ptr [rcx+19h], 2
0x180053721  jb      loc_1800538AD
0x180053727  lea     edx, [r9+0Ch]
0x18005372b  jmp     loc_18005389D
0x180053730  mov     eax, [r14+4]
0x180053734  mov     esi, r13d
0x180053737  test    eax, eax
0x180053739  jz      loc_180053804
0x18005373f  mov     [rbp+57h+pDataIn.cbData], eax
0x180053742  lea     rdx, [rbp+57h+hMem]
0x180053746  lea     rax, [r14+8]
0x18005374a  lea     rcx, [rbp+57h+pDataIn]; pDataIn
0x18005374e  mov     [rbp+57h+pDataIn.pbData], rax
0x180053752  call    DecodeData
0x180053757  mov     esi, eax
0x180053759  test    eax, eax
0x18005375b  jz      short loc_1800537A0
0x18005375d  mov     rcx, cs:WPP_GLOBAL_Control
0x180053764  lea     rax, WPP_GLOBAL_Control
0x18005376b  cmp     rcx, rax
0x18005376e  jz      short loc_180053797
0x180053770  test    dword ptr [rcx+1Ch], 2000h
0x180053777  jz      short loc_180053797
0x180053779  cmp     byte ptr [rcx+19h], 2
0x18005377d  jb      short loc_180053797
0x18005377f  mov     rcx, [rcx+10h]
0x180053783  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x18005378a  mov     edx, 87h
0x18005378f  mov     r9d, esi
0x180053792  call    WPP_SF_d
0x180053797  mov     rdi, [rbp+57h+hMem]
0x18005379b  jmp     loc_1800538AD
0x1800537a0  mov     rdi, [rbp+57h+hMem]
0x1800537a4  cmp     dword ptr [rdi], 50h ; 'P'
0x1800537a7  jnz     short loc_180053804
0x1800537a9  mov     rdx, [rdi+8]; Source2
0x1800537ad  lea     rcx, a5bb789f29e3740; "_$_5bb789f2-9e37-401b-965e-e4de9804aca1"
0x1800537b4  mov     r8d, 50h ; 'P'; Length
0x1800537ba  call    cs:__imp_RtlCompareMemory
0x1800537c0  cmp     rax, 50h ; 'P'
0x1800537c4  jnz     short loc_180053804
0x1800537c6  bts     [rbp+57h+Credential.Flags], 7
0x1800537cb  mov     ecx, [rdi]
0x1800537cd  mov     rax, [rdi+8]
0x1800537d1  test    rcx, rcx
0x1800537d4  jz      short loc_1800537E2
0x1800537d6  mov     [rax], r13b
0x1800537d9  inc     rax
0x1800537dc  sub     rcx, 1
0x1800537e0  jnz     short loc_1800537D6
0x1800537e2  mov     rcx, [rdi+8]; hMem
0x1800537e6  call    cs:__imp_LocalFree
0x1800537ec  mov     rcx, rdi; hMem
0x1800537ef  mov     [rdi+8], r13
0x1800537f3  call    cs:__imp_LocalFree
0x1800537f9  mov     rdi, r13
0x1800537fc  mov     dword ptr [r12], 1
0x180053804  mov     [rbp+57h+Credential.UserName], r15
0x180053808  test    rdi, rdi
0x18005380b  jz      short loc_180053814
0x18005380d  mov     eax, [rdi]
0x18005380f  mov     [rbp+57h+Credential.CredentialBlobSize], eax
0x180053812  jmp     short loc_180053818
0x180053814  mov     [rbp+57h+Credential.CredentialBlobSize], r13d
0x180053818  test    rdi, rdi
0x18005381b  jz      short loc_180053827
0x18005381d  mov     rax, [rdi+8]
0x180053821  mov     [rbp+57h+Credential.CredentialBlob], rax
0x180053825  jmp     short loc_18005382B
0x180053827  mov     [rbp+57h+Credential.CredentialBlob], r13
0x18005382b  xor     r8d, r8d; Flags
0x18005382e  mov     [rbp+57h+Credential.Persist], 1
0x180053835  lea     rcx, TargetName; "*Session"
0x18005383c  mov     [rbp+57h+Credential.TargetName], rcx
0x180053840  lea     edx, [r8+3]; Type
0x180053844  call    cs:__imp_CredDeleteW
0x18005384a  mov     rcx, [rbp+57h+Credential.TargetName]; TargetName
0x18005384e  xor     r8d, r8d; Flags
0x180053851  lea     edx, [r8+2]; Type
0x180053855  call    cs:__imp_CredDeleteW
0x18005385b  xor     edx, edx; Flags
0x18005385d  lea     rcx, [rbp+57h+Credential]; Credential
0x180053861  call    cs:__imp_CredWriteW
0x180053867  test    eax, eax
0x180053869  jnz     short loc_1800538AD
0x18005386b  call    cs:__imp_GetLastError
0x180053871  mov     esi, eax
0x180053873  mov     rcx, cs:WPP_GLOBAL_Control
0x18005387a  lea     rax, WPP_GLOBAL_Control
0x180053881  cmp     rcx, rax
0x180053884  jz      short loc_1800538AD
0x180053886  test    dword ptr [rcx+1Ch], 2000h
0x18005388d  jz      short loc_1800538AD
0x18005388f  cmp     byte ptr [rcx+19h], 2
0x180053893  jb      short loc_1800538AD
0x180053895  mov     edx, 88h
0x18005389a  mov     r9d, esi
0x18005389d  mov     rcx, [rcx+10h]
0x1800538a1  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800538a8  call    WPP_SF_d
0x1800538ad  mov     rcx, r15; hMem
0x1800538b0  call    cs:__imp_LocalFree
0x1800538b6  lea     r15, WPP_GLOBAL_Control
0x1800538bd  mov     rbx, cs:WPP_GLOBAL_Control
0x1800538c4  cmp     [r14+4], r13d
0x1800538c8  jbe     short loc_1800538EA
0x1800538ca  mov     ecx, 800h
0x1800538cf  lea     rax, [r14+8]
0x1800538d3  mov     [rax], r13b
0x1800538d6  inc     rax
0x1800538d9  sub     rcx, 1
0x1800538dd  jnz     short loc_1800538D3
0x1800538df  mov     [r14+4], r13d
0x1800538e3  mov     rbx, cs:WPP_GLOBAL_Control
0x1800538ea  test    rdi, rdi
0x1800538ed  jz      short loc_180053929
0x1800538ef  mov     rax, [rdi+8]
0x1800538f3  test    rax, rax
0x1800538f6  jz      short loc_180053919
0x1800538f8  mov     ecx, [rdi]
0x1800538fa  test    rcx, rcx
0x1800538fd  jz      short loc_18005390B
0x1800538ff  mov     [rax], r13b
0x180053902  inc     rax
0x180053905  sub     rcx, 1
0x180053909  jnz     short loc_1800538FF
0x18005390b  mov     rcx, [rdi+8]; hMem
0x18005390f  call    cs:__imp_LocalFree
0x180053915  mov     [rdi+8], r13
0x180053919  mov     rcx, rdi; hMem
0x18005391c  call    cs:__imp_LocalFree
0x180053922  mov     rbx, cs:WPP_GLOBAL_Control
0x180053929  cmp     rbx, r15
0x18005392c  jz      short loc_180053955
0x18005392e  test    dword ptr [rbx+1Ch], 2000h
0x180053935  jz      short loc_180053955
0x180053937  cmp     byte ptr [rbx+19h], 6
0x18005393b  jb      short loc_180053955
0x18005393d  mov     rcx, [rbx+10h]
0x180053941  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180053948  mov     edx, 89h
0x18005394d  mov     r9d, esi
0x180053950  call    WPP_SF_d
0x180053955  mov     eax, esi
0x180053957  add     rsp, 98h
0x18005395e  pop     r15
0x180053960  pop     r14
0x180053962  pop     r13
0x180053964  pop     r12
0x180053966  pop     rdi
0x180053967  pop     rsi
0x180053968  pop     rbx
0x180053969  pop     rbp
0x18005396a  retn
```
