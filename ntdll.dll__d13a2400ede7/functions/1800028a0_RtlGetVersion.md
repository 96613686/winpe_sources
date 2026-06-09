# RtlGetVersion

- ea: `0x1800028a0`
- end: `0x180002c0e`
- name: `RtlGetVersion`
- size: `878`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x1800012e0`
- `0x180001690`
- `0x180002120`

## callees

- `0x1800028a0`
- `0x180002c20`
- `0x180002c60`
- `0x180021c70`
- `0x1800cc810`
- `0x18012d320`
- `0x1801616d0`
- `0x180161890`
- `0x180162810`
- `0x180164b60`
- `0x18016f030`

## string_xrefs

- `0x180002a05`: `TerminalServices-RemoteConnectionManager-AllowAppServerMode`

## pseudocode

```c
__int64 __fastcall RtlGetVersion(int *a1)
{
  struct _PEB *v2; // r10
  wchar_t *Buffer; // r8
  int v4; // edi
  __int64 result; // rax
  size_t v6; // rax
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  char *p_Str; // rcx
  size_t v14; // rax
  NTSTATUS v15; // eax
  unsigned int v16; // ecx
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh] BYREF
  int v19; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+3Ch] [rbp-C4h] BYREF
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v22; // [rsp+48h] [rbp-B8h] BYREF
  STRING SourceString; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v25[2]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v26; // [rsp+82h] [rbp-7Eh]
  int v27; // [rsp+84h] [rbp-7Ch]
  int v28; // [rsp+88h] [rbp-78h]
  int v29; // [rsp+8Ch] [rbp-74h]
  int v30; // [rsp+90h] [rbp-70h]
  char Str; // [rsp+94h] [rbp-6Ch] BYREF
  char v32; // [rsp+114h] [rbp+14h] BYREF
  char v33; // [rsp+194h] [rbp+94h] BYREF
  char v34; // [rsp+214h] [rbp+114h] BYREF
  char v35; // [rsp+294h] [rbp+194h] BYREF
  char v36; // [rsp+2AEh] [rbp+1AEh] BYREF
  int v37; // [rsp+2C0h] [rbp+1C0h]

  v18 = 0;
  v19 = 0;
  v17 = 0;
  v20 = 0;
  v22 = 0;
  v21 = 0;
  memset_thunk_772440563353939046(v25, 0, 0x244u);
  v2 = NtCurrentPeb();
  DestinationString = 0;
  a1[1] = v2->OSMajorVersion;
  a1[2] = v2->OSMinorVersion;
  a1[3] = v2->OSBuildNumber;
  a1[4] = v2->OSPlatformId;
  Buffer = v2->CSDVersion.Buffer;
  if ( !Buffer || !*Buffer || (int)RtlStringCbCopyW(a1 + 5, 256) < 0 )
    *((_WORD *)a1 + 10) = 0;
  v4 = *a1;
  if ( ((*a1 - 284) & 0xFFFFFFE7) != 0 || v4 == 308 )
    return 0;
  *((_WORD *)a1 + 138) = HIBYTE(v2->OSCSDVersion);
  *((_WORD *)a1 + 139) = (unsigned __int8)v2->OSCSDVersion;
  *((_WORD *)a1 + 140) = RtlGetSuiteMask();
  if ( v4 == 292 )
    a1[71] = RtlGetSuiteMask() & 0x1FFFF;
  *((_BYTE *)a1 + 282) = 0;
  if ( (unsigned __int8)RtlGetNtProductType(&v18) )
    *((_BYTE *)a1 + 282) = v18;
  *(_QWORD *)&v22 = 0;
  *((_QWORD *)&v22 + 1) = L"TerminalServices-RemoteConnectionManager-AllowAppServerMode";
  v6 = 2 * wcslen(L"TerminalServices-RemoteConnectionManager-AllowAppServerMode");
  if ( v6 >= 0xFFFE )
    LOWORD(v6) = -4;
  LOWORD(v22) = v6;
  WORD1(v22) = v6 + 2;
  if ( (int)ZwQueryLicenseValue(&v22, &v19, &v20, 4, &v17) < 0 || v20 != 1 || v19 != 4 || v17 != 4 )
  {
    *((_WORD *)a1 + 140) &= ~0x10u;
    *((_WORD *)a1 + 140) |= 0x100u;
    if ( *a1 == 292 )
    {
      a1[71] &= 0xFFFDFFEF;
      a1[71] |= 0x100u;
    }
  }
  if ( *a1 != 300 )
    return 0;
  v21 = a1[73] & 0xFFF;
  result = NtQuerySystemInformationEx(222, &v21, 4, v25, 580, &v17);
  if ( (int)result < 0 )
    return result;
  v7 = *((unsigned __int16 *)a1 + 146);
  a1[1] = v27;
  a1[2] = v28;
  a1[3] = v29;
  a1[4] = v30;
  v8 = v7 >> 12;
  *((_WORD *)a1 + 147) = v26;
  a1[74] = v37;
  if ( !v8 )
  {
    p_Str = &Str;
    goto LABEL_30;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    p_Str = &v35;
    goto LABEL_30;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    p_Str = &v32;
    goto LABEL_30;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    p_Str = &v36;
    goto LABEL_30;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    if ( v12 == 1 )
    {
      p_Str = &v34;
      goto LABEL_30;
    }
    return 0;
  }
  p_Str = &v33;
LABEL_30:
  *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
  SourceString.Buffer = p_Str;
  v14 = strlen(p_Str);
  *(_DWORD *)&DestinationString.Length = 0x1000000;
  if ( v14 >= 0xFFFF )
    LOWORD(v14) = -2;
  SourceString.Length = v14;
  DestinationString.Buffer = (wchar_t *)(a1 + 5);
  SourceString.MaximumLength = v14 + 1;
  v15 = RtlAnsiStringToUnicodeString(&DestinationString, &SourceString, 0);
  v16 = 0;
  if ( v15 < 0 )
    return (unsigned int)v15;
  return v16;
}

```

## disassembly

```asm
0x1800028a0  mov     [rsp-8+arg_8], rbx
0x1800028a5  mov     [rsp-8+arg_10], rsi
0x1800028aa  push    rbp
0x1800028ab  push    rdi
0x1800028ac  push    r14
0x1800028ae  lea     rbp, [rsp-1E0h]
0x1800028b6  sub     rsp, 2E0h
0x1800028bd  mov     rax, cs:__security_cookie
0x1800028c4  xor     rax, rsp
0x1800028c7  mov     [rbp+1F0h+var_20], rax
0x1800028ce  xor     esi, esi
0x1800028d0  mov     rbx, rcx
0x1800028d3  xorps   xmm0, xmm0
0x1800028d6  mov     [rsp+2F0h+var_2BC], esi
0x1800028da  lea     rcx, [rbp+1F0h+var_270]; void *
0x1800028de  mov     [rsp+2F0h+var_2B8], esi
0x1800028e2  xor     edx, edx; Val
0x1800028e4  mov     [rsp+2F0h+var_2C0], esi
0x1800028e8  mov     r8d, 244h; Size
0x1800028ee  mov     [rsp+2F0h+var_2B4], esi
0x1800028f2  movups  [rsp+2F0h+var_2A8], xmm0
0x1800028f7  mov     [rsp+2F0h+var_2B0], esi
0x1800028fb  call    memset$thunk$772440563353939046
0x180002900  mov     r10, gs:60h
0x180002909  xorps   xmm0, xmm0
0x18000290c  movups  xmmword ptr [rsp+2F0h+DestinationString.Length], xmm0
0x180002911  mov     r14d, 100h
0x180002917  mov     eax, [r10+118h]
0x18000291e  mov     [rbx+4], eax
0x180002921  mov     eax, [r10+11Ch]
0x180002928  mov     [rbx+8], eax
0x18000292b  movzx   eax, word ptr [r10+120h]
0x180002933  mov     [rbx+0Ch], eax
0x180002936  mov     eax, [r10+124h]
0x18000293d  mov     [rbx+10h], eax
0x180002940  mov     r8, [r10+2F0h]
0x180002947  test    r8, r8
0x18000294a  jz      short loc_180002956
0x18000294c  cmp     [r8], si
0x180002950  jnz     loc_180002BF5
0x180002956  mov     [rbx+14h], si
0x18000295a  mov     edi, [rbx]
0x18000295c  lea     eax, [rdi-11Ch]
0x180002962  test    eax, 0FFFFFFE7h
0x180002967  jz      short loc_180002993
0x180002969  xor     eax, eax
0x18000296b  mov     rcx, [rbp+1F0h+var_20]
0x180002972  xor     rcx, rsp; StackCookie
0x180002975  call    __security_check_cookie
0x18000297a  lea     r11, [rsp+2F0h+var_10]
0x180002982  mov     rbx, [r11+28h]
0x180002986  mov     rsi, [r11+30h]
0x18000298a  mov     rsp, r11
0x18000298d  pop     r14
0x18000298f  pop     rdi
0x180002990  pop     rbp
0x180002991  retn
0x180002993  cmp     edi, 134h
0x180002999  jz      short loc_180002969
0x18000299b  movzx   eax, byte ptr [r10+123h]
0x1800029a3  mov     ecx, 0FFh
0x1800029a8  mov     [rbx+114h], ax
0x1800029af  movzx   eax, word ptr [r10+122h]
0x1800029b7  and     ax, cx
0x1800029ba  mov     [rbx+116h], ax
0x1800029c1  call    RtlGetSuiteMask
0x1800029c6  mov     [rbx+118h], ax
0x1800029cd  cmp     edi, 124h
0x1800029d3  jnz     short loc_1800029E5
0x1800029d5  call    RtlGetSuiteMask
0x1800029da  and     eax, 1FFFFh
0x1800029df  mov     [rbx+11Ch], eax
0x1800029e5  lea     rcx, [rsp+2F0h+var_2BC]
0x1800029ea  mov     [rbx+11Ah], sil
0x1800029f1  call    RtlGetNtProductType
0x1800029f6  test    al, al
0x1800029f8  jz      short loc_180002A05
0x1800029fa  movzx   eax, byte ptr [rsp+2F0h+var_2BC]
0x1800029ff  mov     [rbx+11Ah], al
0x180002a05  lea     rcx, aTerminalservic; "TerminalServices-RemoteConnectionManage"...
0x180002a0c  mov     qword ptr [rsp+2F0h+var_2A8], rsi
0x180002a11  mov     qword ptr [rsp+2F0h+var_2A8+8], rcx
0x180002a16  call    wcslen
0x180002a1b  add     rax, rax
0x180002a1e  lea     r8, [rsp+2F0h+var_2B4]
0x180002a23  mov     ecx, 0FFFCh
0x180002a28  lea     rdx, [rsp+2F0h+var_2B8]
0x180002a2d  mov     edi, 0FFFEh
0x180002a32  mov     r9d, 4
0x180002a38  cmp     rax, rdi
0x180002a3b  cmovnb  rax, rcx
0x180002a3f  lea     rcx, [rsp+2F0h+var_2A8]
0x180002a44  mov     word ptr [rsp+2F0h+var_2A8], ax
0x180002a49  add     ax, 2
0x180002a4d  mov     word ptr [rsp+2F0h+var_2A8+2], ax
0x180002a52  lea     rax, [rsp+2F0h+var_2C0]
0x180002a57  mov     [rsp+2F0h+var_2D0], rax
0x180002a5c  call    ZwQueryLicenseValue
0x180002a61  test    eax, eax
0x180002a63  js      short loc_180002A70
0x180002a65  cmp     [rsp+2F0h+var_2B4], 1
0x180002a6a  jz      loc_180002B56
0x180002a70  mov     eax, 0FFEFh
0x180002a75  and     [rbx+118h], ax
0x180002a7c  or      [rbx+118h], r14w
0x180002a84  cmp     dword ptr [rbx], 124h
0x180002a8a  jnz     short loc_180002A9D
0x180002a8c  and     dword ptr [rbx+11Ch], 0FFFDFFEFh
0x180002a96  or      [rbx+11Ch], r14d
0x180002a9d  cmp     dword ptr [rbx], 12Ch
0x180002aa3  jnz     loc_180002969
0x180002aa9  movzx   eax, word ptr [rbx+124h]
0x180002ab0  lea     r9, [rbp+1F0h+var_270]
0x180002ab4  and     eax, 0FFFh
0x180002ab9  lea     rdx, [rsp+2F0h+var_2B0]
0x180002abe  mov     [rsp+2F0h+var_2B0], eax
0x180002ac2  mov     r8d, 4
0x180002ac8  lea     rax, [rsp+2F0h+var_2C0]
0x180002acd  mov     ecx, 0DEh
0x180002ad2  mov     [rsp+2F0h+var_2C8], rax
0x180002ad7  mov     dword ptr [rsp+2F0h+var_2D0], 244h
0x180002adf  call    NtQuerySystemInformationEx
0x180002ae4  test    eax, eax
0x180002ae6  js      loc_18000296B
0x180002aec  mov     eax, [rbp+1F0h+var_26C]
0x180002aef  movzx   ecx, word ptr [rbx+124h]
0x180002af6  mov     [rbx+4], eax
0x180002af9  mov     eax, [rbp+1F0h+var_268]
0x180002afc  mov     [rbx+8], eax
0x180002aff  mov     eax, [rbp+1F0h+var_264]
0x180002b02  mov     [rbx+0Ch], eax
0x180002b05  mov     eax, [rbp+1F0h+var_260]
0x180002b08  mov     [rbx+10h], eax
0x180002b0b  movzx   eax, [rbp+1F0h+var_26E]
0x180002b0f  shr     ecx, 0Ch
0x180002b12  mov     [rbx+126h], ax
0x180002b19  mov     eax, [rbp+1F0h+var_30]
0x180002b1f  mov     [rbx+128h], eax
0x180002b25  test    ecx, ecx
0x180002b27  jz      short loc_180002B71
0x180002b29  sub     ecx, 1
0x180002b2c  jz      loc_180002BDA
0x180002b32  sub     ecx, 1
0x180002b35  jz      loc_180002BCB
0x180002b3b  sub     ecx, 1
0x180002b3e  jz      loc_180002BD1
0x180002b44  sub     ecx, 1
0x180002b47  jnz     loc_180002BE3
0x180002b4d  lea     rcx, [rbp+1F0h+var_15C]
0x180002b54  jmp     short loc_180002B75
0x180002b56  cmp     [rsp+2F0h+var_2B8], 4
0x180002b5b  jnz     loc_180002A70
0x180002b61  cmp     [rsp+2F0h+var_2C0], 4
0x180002b66  jz      loc_180002A9D
0x180002b6c  jmp     loc_180002A70
0x180002b71  lea     rcx, [rbp+1F0h+Str]; Str
0x180002b75  mov     dword ptr [rsp+2F0h+SourceString+4], esi
0x180002b79  mov     [rsp+2F0h+SourceString.Buffer], rcx
0x180002b7e  call    strlen
0x180002b83  cmp     rax, 0FFFFh
0x180002b89  mov     dword ptr [rsp+2F0h+DestinationString.Length], 1000000h
0x180002b91  lea     rdx, [rsp+2F0h+SourceString]; SourceString
0x180002b96  cmovnb  rax, rdi
0x180002b9a  lea     rcx, [rsp+2F0h+DestinationString]; DestinationString
0x180002b9f  mov     [rsp+2F0h+SourceString.Length], ax
0x180002ba4  add     rbx, 14h
0x180002ba8  inc     ax
0x180002bab  mov     [rsp+2F0h+DestinationString.Buffer], rbx
0x180002bb0  xor     r8d, r8d; AllocateDestinationString
0x180002bb3  mov     [rsp+2F0h+SourceString.MaximumLength], ax
0x180002bb8  call    RtlAnsiStringToUnicodeString
0x180002bbd  test    eax, eax
0x180002bbf  mov     ecx, esi
0x180002bc1  cmovs   ecx, eax
0x180002bc4  mov     eax, ecx
0x180002bc6  jmp     loc_18000296B
0x180002bcb  lea     rcx, [rbp+1F0h+var_1DC]
0x180002bcf  jmp     short loc_180002B75
0x180002bd1  lea     rcx, [rbp+1F0h+var_42]
0x180002bd8  jmp     short loc_180002B75
0x180002bda  lea     rcx, [rbp+1F0h+var_5C]
0x180002be1  jmp     short loc_180002B75
0x180002be3  cmp     ecx, 1
0x180002be6  jnz     loc_180002969
0x180002bec  lea     rcx, [rbp+1F0h+var_DC]
0x180002bf3  jmp     short loc_180002B75
0x180002bf5  mov     rdx, r14
0x180002bf8  lea     rcx, [rbx+14h]
0x180002bfc  call    RtlStringCbCopyW
0x180002c01  test    eax, eax
0x180002c03  js      loc_180002956
0x180002c09  jmp     loc_18000295A
```
