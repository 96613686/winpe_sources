# SaveCredentialsInCredManW

- ea: `0x180055c80`
- end: `0x180056171`
- name: `SaveCredentialsInCredManW`
- size: `1265`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180055360`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000eb54`
- `0x18003b72c`
- `0x180055c80`
- `0x1800e8e96`

## import_xrefs

- `msvcrt!wcspbrk` at `0x180055e02`
- `msvcrt!wcspbrk` at `0x180055e02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056058`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056058`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180055d52`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180055d52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055fb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055fc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800560a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056108`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005611b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055fb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055fc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800560a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056108`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005611b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180055f83`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x180055f83`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18005601f`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180056036`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18005601f`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180056036`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180056048`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x180056048`

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
0x180055c80  push    rbp
0x180055c82  push    rbx
0x180055c83  push    rsi
0x180055c84  push    rdi
0x180055c85  push    r12
0x180055c87  push    r13
0x180055c89  push    r14
0x180055c8b  push    r15
0x180055c8d  lea     rbp, [rsp-1Fh]
0x180055c92  sub     rsp, 98h
0x180055c99  mov     r12, rdx
0x180055c9c  mov     r14, rcx
0x180055c9f  mov     rbx, cs:WPP_GLOBAL_Control
0x180055ca6  lea     r15, WPP_GLOBAL_Control
0x180055cad  cmp     rbx, r15
0x180055cb0  jz      short loc_180055CDD
0x180055cb2  test    dword ptr [rbx+1Ch], 2000h
0x180055cb9  jz      short loc_180055CDD
0x180055cbb  cmp     byte ptr [rbx+19h], 6
0x180055cbf  jb      short loc_180055CDD
0x180055cc1  mov     rcx, [rbx+10h]
0x180055cc5  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180055ccc  mov     edx, 82h
0x180055cd1  call    WPP_SF_
0x180055cd6  mov     rbx, cs:WPP_GLOBAL_Control
0x180055cdd  mov     esi, 50h ; 'P'
0x180055ce2  lea     rcx, [rbp+57h+Credential]; void *
0x180055ce6  mov     r8d, esi; Size
0x180055ce9  xor     edx, edx; Val
0x180055ceb  call    memset_0
0x180055cf0  xor     eax, eax
0x180055cf2  xor     r13d, r13d
0x180055cf5  test    byte ptr [r14], 16h
0x180055cf9  mov     edi, r13d
0x180055cfc  mov     qword ptr [rbp+57h+pDataIn+4], rax
0x180055d00  mov     [rbp-49h], rax
0x180055d04  mov     [rbp+57h+hMem], r13
0x180055d08  jnz     short loc_180055D48
0x180055d0a  lea     esi, [rax+32h]
0x180055d0d  cmp     rbx, r15
0x180055d10  jz      loc_1800560BD
0x180055d16  test    dword ptr [rbx+1Ch], 2000h
0x180055d1d  jz      loc_1800560BD
0x180055d23  cmp     byte ptr [rbx+19h], 2
0x180055d27  jb      loc_1800560BD
0x180055d2d  lea     edx, [rsi+51h]
0x180055d30  mov     r9d, esi
0x180055d33  mov     rcx, [rbx+10h]
0x180055d37  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180055d3e  call    WPP_SF_d
0x180055d43  jmp     loc_1800560B6
0x180055d48  mov     edx, 200h; uBytes
0x180055d4d  mov     ecx, 40h ; '@'; uFlags
0x180055d52  call    cs:__imp_LocalAlloc
0x180055d59  nop     dword ptr [rax+rax+00h]
0x180055d5e  mov     r15, rax
0x180055d61  test    rax, rax
0x180055d64  jnz     short loc_180055DB7
0x180055d66  call    cs:__imp_GetLastError
0x180055d6d  nop     dword ptr [rax+rax+00h]
0x180055d72  mov     esi, eax
0x180055d74  test    eax, eax
0x180055d76  jz      loc_1800560AF
0x180055d7c  mov     rbx, cs:WPP_GLOBAL_Control
0x180055d83  lea     r15, WPP_GLOBAL_Control
0x180055d8a  cmp     rbx, r15
0x180055d8d  jz      loc_1800560BD
0x180055d93  test    dword ptr [rbx+1Ch], 2000h
0x180055d9a  jz      loc_1800560BD
0x180055da0  cmp     byte ptr [rbx+19h], 2
0x180055da4  jb      loc_1800560BD
0x180055daa  mov     edx, 84h
0x180055daf  mov     r9d, eax
0x180055db2  jmp     loc_180055D33
0x180055db7  mov     rcx, rsi
0x180055dba  lea     rax, [rbp+57h+Credential]
0x180055dbe  mov     [rax], r13b
0x180055dc1  inc     rax
0x180055dc4  sub     rcx, 1
0x180055dc8  jnz     short loc_180055DBE
0x180055dca  test    byte ptr [r14], 4
0x180055dce  lea     rbx, [r14+0A08h]
0x180055dd5  jz      short loc_180055DE0
0x180055dd7  mov     [rbp+57h+Credential.Type], 2
0x180055dde  jmp     short loc_180055DEB
0x180055de0  mov     [rbx], r13w
0x180055de4  mov     [rbp+57h+Credential.Type], 3
0x180055deb  lea     rsi, [r14+808h]
0x180055df2  cmp     r13w, [rbx]
0x180055df6  jz      short loc_180055E77
0x180055df8  lea     rdx, asc_1800F3124; "@\\"
0x180055dff  mov     rcx, rsi; String
0x180055e02  call    cs:__imp_wcspbrk
0x180055e09  nop     dword ptr [rax+rax+00h]
0x180055e0e  test    rax, rax
0x180055e11  jnz     short loc_180055E77
0x180055e13  mov     r9, rbx
0x180055e16  mov     [rsp+0D0h+var_B0], rsi
0x180055e1b  lea     r8, aSS_2; "%s\\%s"
0x180055e22  mov     edx, 100h; unsigned __int64
0x180055e27  mov     rcx, r15; unsigned __int16 *
0x180055e2a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055e2f  test    eax, eax
0x180055e31  jz      loc_180055EF9
0x180055e37  mov     r9d, 7Ah ; 'z'
0x180055e3d  mov     esi, r9d
0x180055e40  mov     rcx, cs:WPP_GLOBAL_Control
0x180055e47  lea     rax, WPP_GLOBAL_Control
0x180055e4e  cmp     rcx, rax
0x180055e51  jz      loc_1800560A0
0x180055e57  test    dword ptr [rcx+1Ch], 2000h
0x180055e5e  jz      loc_1800560A0
0x180055e64  cmp     byte ptr [rcx+19h], 2
0x180055e68  jb      loc_1800560A0
0x180055e6e  lea     edx, [r9+0Bh]
0x180055e72  jmp     loc_180056090
0x180055e77  mov     ecx, 7FFFFFFEh
0x180055e7c  mov     edx, 100h
0x180055e81  mov     rax, r15
0x180055e84  test    rcx, rcx
0x180055e87  jz      short loc_180055EA8
0x180055e89  movzx   r8d, word ptr [rsi]
0x180055e8d  test    r8w, r8w
0x180055e91  jz      short loc_180055EA8
0x180055e93  mov     [rax], r8w
0x180055e97  add     rsi, 2
0x180055e9b  add     rax, 2
0x180055e9f  dec     rcx
0x180055ea2  sub     rdx, 1
0x180055ea6  jnz     short loc_180055E84
0x180055ea8  test    rdx, rdx
0x180055eab  lea     rcx, [rax-2]
0x180055eaf  cmovnz  rcx, rax
0x180055eb3  mov     [rcx], r13w
0x180055eb7  jnz     short loc_180055EF9
0x180055eb9  mov     r9d, 7Ah ; 'z'
0x180055ebf  mov     esi, r9d
0x180055ec2  mov     rcx, cs:WPP_GLOBAL_Control
0x180055ec9  lea     rax, WPP_GLOBAL_Control
0x180055ed0  cmp     rcx, rax
0x180055ed3  jz      loc_1800560A0
0x180055ed9  test    dword ptr [rcx+1Ch], 2000h
0x180055ee0  jz      loc_1800560A0
0x180055ee6  cmp     byte ptr [rcx+19h], 2
0x180055eea  jb      loc_1800560A0
0x180055ef0  lea     edx, [r9+0Ch]
0x180055ef4  jmp     loc_180056090
0x180055ef9  mov     eax, [r14+4]
0x180055efd  mov     esi, r13d
0x180055f00  test    eax, eax
0x180055f02  jz      loc_180055FDF
0x180055f08  mov     [rbp+57h+pDataIn.cbData], eax
0x180055f0b  lea     rdx, [rbp+57h+hMem]
0x180055f0f  lea     rax, [r14+8]
0x180055f13  lea     rcx, [rbp+57h+pDataIn]; pDataIn
0x180055f17  mov     [rbp+57h+pDataIn.pbData], rax
0x180055f1b  call    DecodeData
0x180055f20  mov     esi, eax
0x180055f22  test    eax, eax
0x180055f24  jz      short loc_180055F69
0x180055f26  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f2d  lea     rax, WPP_GLOBAL_Control
0x180055f34  cmp     rcx, rax
0x180055f37  jz      short loc_180055F60
0x180055f39  test    dword ptr [rcx+1Ch], 2000h
0x180055f40  jz      short loc_180055F60
0x180055f42  cmp     byte ptr [rcx+19h], 2
0x180055f46  jb      short loc_180055F60
0x180055f48  mov     rcx, [rcx+10h]
0x180055f4c  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180055f53  mov     edx, 87h
0x180055f58  mov     r9d, esi
0x180055f5b  call    WPP_SF_d
0x180055f60  mov     rdi, [rbp+57h+hMem]
0x180055f64  jmp     loc_1800560A0
0x180055f69  mov     rdi, [rbp+57h+hMem]
0x180055f6d  cmp     dword ptr [rdi], 50h ; 'P'
0x180055f70  jnz     short loc_180055FDF
0x180055f72  mov     rdx, [rdi+8]; Source2
0x180055f76  lea     rcx, a5bb789f29e3740; "_$_5bb789f2-9e37-401b-965e-e4de9804aca1"
0x180055f7d  mov     r8d, 50h ; 'P'; Length
0x180055f83  call    cs:__imp_RtlCompareMemory
0x180055f8a  nop     dword ptr [rax+rax+00h]
0x180055f8f  cmp     rax, 50h ; 'P'
0x180055f93  jnz     short loc_180055FDF
0x180055f95  bts     [rbp+57h+Credential.Flags], 7
0x180055f9a  mov     ecx, [rdi]
0x180055f9c  mov     rax, [rdi+8]
0x180055fa0  test    rcx, rcx
0x180055fa3  jz      short loc_180055FB1
0x180055fa5  mov     [rax], r13b
0x180055fa8  inc     rax
0x180055fab  sub     rcx, 1
0x180055faf  jnz     short loc_180055FA5
0x180055fb1  mov     rcx, [rdi+8]; hMem
0x180055fb5  call    cs:__imp_LocalFree
0x180055fbc  nop     dword ptr [rax+rax+00h]
0x180055fc1  mov     rcx, rdi; hMem
0x180055fc4  mov     [rdi+8], r13
0x180055fc8  call    cs:__imp_LocalFree
0x180055fcf  nop     dword ptr [rax+rax+00h]
0x180055fd4  mov     rdi, r13
0x180055fd7  mov     dword ptr [r12], 1
0x180055fdf  mov     [rbp+57h+Credential.UserName], r15
0x180055fe3  test    rdi, rdi
0x180055fe6  jz      short loc_180055FEF
0x180055fe8  mov     eax, [rdi]
0x180055fea  mov     [rbp+57h+Credential.CredentialBlobSize], eax
0x180055fed  jmp     short loc_180055FF3
0x180055fef  mov     [rbp+57h+Credential.CredentialBlobSize], r13d
0x180055ff3  test    rdi, rdi
0x180055ff6  jz      short loc_180056002
0x180055ff8  mov     rax, [rdi+8]
0x180055ffc  mov     [rbp+57h+Credential.CredentialBlob], rax
0x180056000  jmp     short loc_180056006
0x180056002  mov     [rbp+57h+Credential.CredentialBlob], r13
0x180056006  xor     r8d, r8d; Flags
0x180056009  mov     [rbp+57h+Credential.Persist], 1
0x180056010  lea     rcx, TargetName; "*Session"
0x180056017  mov     [rbp+57h+Credential.TargetName], rcx
0x18005601b  lea     edx, [r8+3]; Type
0x18005601f  call    cs:__imp_CredDeleteW
0x180056026  nop     dword ptr [rax+rax+00h]
0x18005602b  mov     rcx, [rbp+57h+Credential.TargetName]; TargetName
0x18005602f  xor     r8d, r8d; Flags
0x180056032  lea     edx, [r8+2]; Type
0x180056036  call    cs:__imp_CredDeleteW
0x18005603d  nop     dword ptr [rax+rax+00h]
0x180056042  xor     edx, edx; Flags
0x180056044  lea     rcx, [rbp+57h+Credential]; Credential
0x180056048  call    cs:__imp_CredWriteW
0x18005604f  nop     dword ptr [rax+rax+00h]
0x180056054  test    eax, eax
0x180056056  jnz     short loc_1800560A0
0x180056058  call    cs:__imp_GetLastError
0x18005605f  nop     dword ptr [rax+rax+00h]
0x180056064  mov     esi, eax
0x180056066  mov     rcx, cs:WPP_GLOBAL_Control
0x18005606d  lea     rax, WPP_GLOBAL_Control
0x180056074  cmp     rcx, rax
0x180056077  jz      short loc_1800560A0
0x180056079  test    dword ptr [rcx+1Ch], 2000h
0x180056080  jz      short loc_1800560A0
0x180056082  cmp     byte ptr [rcx+19h], 2
0x180056086  jb      short loc_1800560A0
0x180056088  mov     edx, 88h
0x18005608d  mov     r9d, esi
0x180056090  mov     rcx, [rcx+10h]
0x180056094  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x18005609b  call    WPP_SF_d
0x1800560a0  mov     rcx, r15; hMem
0x1800560a3  call    cs:__imp_LocalFree
0x1800560aa  nop     dword ptr [rax+rax+00h]
0x1800560af  lea     r15, WPP_GLOBAL_Control
0x1800560b6  mov     rbx, cs:WPP_GLOBAL_Control
0x1800560bd  cmp     [r14+4], r13d
0x1800560c1  jbe     short loc_1800560E3
0x1800560c3  mov     ecx, 800h
0x1800560c8  lea     rax, [r14+8]
0x1800560cc  mov     [rax], r13b
0x1800560cf  inc     rax
0x1800560d2  sub     rcx, 1
0x1800560d6  jnz     short loc_1800560CC
0x1800560d8  mov     [r14+4], r13d
0x1800560dc  mov     rbx, cs:WPP_GLOBAL_Control
0x1800560e3  test    rdi, rdi
0x1800560e6  jz      short loc_18005612E
0x1800560e8  mov     rax, [rdi+8]
0x1800560ec  test    rax, rax
0x1800560ef  jz      short loc_180056118
0x1800560f1  mov     ecx, [rdi]
0x1800560f3  test    rcx, rcx
0x1800560f6  jz      short loc_180056104
0x1800560f8  mov     [rax], r13b
0x1800560fb  inc     rax
0x1800560fe  sub     rcx, 1
0x180056102  jnz     short loc_1800560F8
0x180056104  mov     rcx, [rdi+8]; hMem
0x180056108  call    cs:__imp_LocalFree
0x18005610f  nop     dword ptr [rax+rax+00h]
0x180056114  mov     [rdi+8], r13
0x180056118  mov     rcx, rdi; hMem
0x18005611b  call    cs:__imp_LocalFree
0x180056122  nop     dword ptr [rax+rax+00h]
0x180056127  mov     rbx, cs:WPP_GLOBAL_Control
0x18005612e  cmp     rbx, r15
0x180056131  jz      short loc_18005615A
0x180056133  test    dword ptr [rbx+1Ch], 2000h
0x18005613a  jz      short loc_18005615A
0x18005613c  cmp     byte ptr [rbx+19h], 6
0x180056140  jb      short loc_18005615A
0x180056142  mov     rcx, [rbx+10h]
0x180056146  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x18005614d  mov     edx, 89h
0x180056152  mov     r9d, esi
0x180056155  call    WPP_SF_d
0x18005615a  mov     eax, esi
0x18005615c  add     rsp, 98h
0x180056163  pop     r15
0x180056165  pop     r14
  ... truncated ...
```
