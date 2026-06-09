# UserAgent::UserAgent(void)

- ea: `0x100461cf4`
- end: `0x1004620dd`
- name: `??0UserAgent@@QEAA@XZ`
- size: `1001`
- prototype: `UserAgent *__fastcall(UserAgent *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x100462b10`

## callees

- `0x100461cf4`
- `0x100462188`
- `0x100547ef0`
- `0x100548140`
- `0x100548164`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x100461eab`
- `KERNEL32!GetSystemInfo` at `0x100461eab`
- `KERNEL32!GetModuleHandleW` at `0x100461da5`
- `KERNEL32!GetModuleHandleW` at `0x100461da5`
- `KERNEL32!GetProcAddress` at `0x100461dbe`
- `KERNEL32!GetProcAddress` at `0x100461dbe`

## string_xrefs

- `0x100461d9e`: `ntdll.dll`

## pseudocode

```c
UserAgent *__fastcall UserAgent::UserAgent(UserAgent *this)
{
  UserAgent *v1; // rbx
  unsigned __int64 v2; // rcx
  UserAgent *v3; // rax
  __int16 v4; // r8
  char *v5; // r14
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned __int64 v8; // rax
  __int64 v9; // rdi
  unsigned __int64 v10; // rcx
  _WORD *v11; // rax
  __int16 v12; // r8
  const wchar_t *v13; // rax
  unsigned __int64 v14; // rdx
  _WORD *v15; // rcx
  signed __int64 v16; // rax
  __int16 v17; // r8
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rax
  unsigned __int64 v25; // r8
  _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-238h] BYREF
  int v28; // [rsp+80h] [rbp-208h] BYREF
  _DWORD v29[71]; // [rsp+84h] [rbp-204h] BYREF
  wchar_t v30[32]; // [rsp+1A0h] [rbp-E8h] BYREF
  wchar_t Buffer[64]; // [rsp+1E0h] [rbp-A8h] BYREF

  v1 = this;
  *((_QWORD *)this + 104) = 0;
  v2 = 0;
  v3 = v1;
  do
  {
    v4 = *(_WORD *)((char *)v3 + (char *)L"Windows" - (char *)v1);
    if ( !v4 )
      break;
    *(_WORD *)v3 = v4;
    ++v2;
    v3 = (UserAgent *)((char *)v3 + 2);
  }
  while ( v2 < 0xF );
  try
  {
    *((_WORD *)v1 + 15) = 0;
    v5 = (char *)v1 + 32;
    if ( v1 != (UserAgent *)-32LL )
    {
      memset_0(v29, 0, 0x110u);
      v28 = 276;
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      if ( ModuleHandleW
        && (ProcAddress = GetProcAddress(ModuleHandleW, "RtlGetVersion")) != 0
        && !((unsigned int (__fastcall *)(int *))ProcAddress)(&v28)
        && swprintf_s(Buffer, 0x40u, L"Windows %d.%d.%d.0", v29[0], v29[1], v29[2]) > 0 )
      {
        v8 = -1;
        do
          ++v8;
        while ( Buffer[v8] );
        v9 = 127;
        if ( v8 < 0x7F )
          v9 = v8;
        if ( v9 )
          memcpy_0((char *)v1 + 32, Buffer, 2 * v9);
        *(_WORD *)&v5[2 * v9] = 0;
      }
      else
      {
        v10 = 0;
        v11 = (_WORD *)((char *)v1 + 32);
        do
        {
          v12 = *(_WORD *)((char *)v11 + (char *)L"Unknown" - v5);
          if ( !v12 )
            break;
          *v11 = v12;
          ++v10;
          ++v11;
        }
        while ( v10 < 0x7F );
        *((_WORD *)v1 + 143) = 0;
      }
    }
    if ( v1 != (UserAgent *)-288LL )
    {
      GetSystemInfo(&SystemInfo);
      v13 = L"Unknown";
      if ( SystemInfo.wProcessorArchitecture )
      {
        if ( SystemInfo.wProcessorArchitecture == 9 )
        {
          v13 = L"amd64";
        }
        else if ( SystemInfo.wProcessorArchitecture == 12 )
        {
          v13 = L"arm64";
        }
      }
      else
      {
        v13 = L"x86";
      }
      v14 = 0;
      v15 = (_WORD *)((char *)v1 + 288);
      v16 = (char *)v13 - ((char *)v1 + 288);
      do
      {
        v17 = *(_WORD *)((char *)v15 + v16);
        if ( !v17 )
          break;
        *v15 = v17;
        ++v14;
        ++v15;
      }
      while ( v14 < 0xF );
      *((_WORD *)v1 + 159) = 0;
    }
    UserAgent::AppendFilteredField(v1, L"1", 2u);
    v18 = *((_QWORD *)v1 + 104);
    if ( v18 < 0xFF )
    {
      *((_WORD *)v1 + v18 + 160) = 124;
      ++*((_QWORD *)v1 + 104);
    }
    UserAgent::AppendFilteredField(v1, L"MS-ODBC", 0xCu);
    v19 = *((_QWORD *)v1 + 104);
    if ( v19 < 0xFF )
    {
      *((_WORD *)v1 + v19 + 160) = 124;
      ++*((_QWORD *)v1 + 104);
    }
    memset_0(v30, 0, sizeof(v30));
    if ( swprintf_s(v30, 0x20u, L"%d.%d.%d.%d") < 0 )
      v30[0] = 0;
    UserAgent::AppendFilteredField(v1, v30, 0x18u);
    v20 = *((_QWORD *)v1 + 104);
    if ( v20 < 0xFF )
    {
      *((_WORD *)v1 + v20 + 160) = 124;
      ++*((_QWORD *)v1 + 104);
    }
    UserAgent::AppendFilteredField(v1, (const char16_t *)v1 + 144, 0xAu);
    v21 = *((_QWORD *)v1 + 104);
    if ( v21 < 0xFF )
    {
      *((_WORD *)v1 + v21 + 160) = 124;
      ++*((_QWORD *)v1 + 104);
    }
    UserAgent::AppendFilteredField(v1, (const char16_t *)v1, 0xAu);
    v22 = *((_QWORD *)v1 + 104);
    if ( v22 < 0xFF )
    {
      *((_WORD *)v1 + v22 + 160) = 124;
      ++*((_QWORD *)v1 + 104);
    }
    UserAgent::AppendFilteredField(v1, (const char16_t *)v1 + 16, 0x2Cu);
    v23 = *((_QWORD *)v1 + 104);
    if ( v23 < 0xFF )
    {
      *((_WORD *)v1 + v23 + 160) = 124;
      ++*((_QWORD *)v1 + 104);
    }
    UserAgent::AppendFilteredField(v1, L"Unknown", 0x2Cu);
    *((_WORD *)v1 + *((_QWORD *)v1 + 104) + 160) = 0;
  }
  catch ( ... )
  {
    *((_QWORD *)this + 104) = 0;
    v25 = 0;
    do
    {
      if ( v25 >= 255 )
        break;
      *((_WORD *)this + (*((_QWORD *)this + 104))++ + 160) = a1MsOdbcUnknown[v25++];
    }
    while ( a1MsOdbcUnknown[v25] );
    *((_WORD *)this + *((_QWORD *)this + 104) + 160) = 0;
    return this;
  }
  return v1;
}

```

## disassembly

```asm
0x100461cf4  mov     rax, rsp
0x100461cf7  push    r13
0x100461cf9  push    r14
0x100461cfb  push    r15
0x100461cfd  sub     rsp, 270h
0x100461d04  mov     [rsp+288h+var_240], 0FFFFFFFFFFFFFFFEh
0x100461d0d  mov     [rax+10h], rbx
0x100461d11  mov     [rax+18h], rsi
0x100461d15  mov     [rax+20h], rdi
0x100461d19  mov     rax, cs:__security_cookie
0x100461d20  xor     rax, rsp
0x100461d23  mov     [rsp+288h+var_28], rax
0x100461d2b  mov     rbx, rcx
0x100461d2e  mov     [rsp+288h+var_248], rcx
0x100461d33  xor     r15d, r15d
0x100461d36  mov     [rcx+340h], r15
0x100461d3d  mov     ecx, r15d
0x100461d40  mov     rax, rbx
0x100461d43  lea     rdx, aWindows; "Windows"
0x100461d4a  sub     rdx, rbx
0x100461d4d  lea     r13d, [r15+2]
0x100461d51  movzx   r8d, word ptr [rdx+rax]
0x100461d56  test    r8w, r8w
0x100461d5a  jz      short loc_100461D6C
0x100461d5c  mov     [rax], r8w
0x100461d60  inc     rcx
0x100461d63  add     rax, r13
0x100461d66  cmp     rcx, 0Fh
0x100461d6a  jb      short loc_100461D51
0x100461d6c  mov     [rbx+1Eh], r15w
0x100461d71  lea     r14, [rbx+20h]
0x100461d75  test    r14, r14
0x100461d78  jz      loc_100461E9A
0x100461d7e  xor     edx, edx; Val
0x100461d80  mov     r8d, 110h; Size
0x100461d86  lea     rcx, [rsp+288h+var_204]; void *
0x100461d8e  call    memset_0
0x100461d93  mov     [rsp+288h+var_208], 114h
0x100461d9e  lea     rcx, ModuleName; "ntdll.dll"
0x100461da5  call    cs:__imp_GetModuleHandleW
0x100461dab  test    rax, rax
0x100461dae  jz      loc_100461E63
0x100461db4  lea     rdx, aRtlgetversion; "RtlGetVersion"
0x100461dbb  mov     rcx, rax; hModule
0x100461dbe  call    cs:__imp_GetProcAddress
0x100461dc4  test    rax, rax
0x100461dc7  jz      loc_100461E63
0x100461dcd  lea     rcx, [rsp+288h+var_208]
0x100461dd5  call    cs:__guard_dispatch_icall_fptr
0x100461ddb  test    eax, eax
0x100461ddd  jnz     loc_100461E63
0x100461de3  mov     eax, [rsp+288h+var_1FC]
0x100461dea  mov     [rsp+288h+var_260], eax
0x100461dee  mov     eax, [rsp+288h+var_200]
0x100461df5  mov     [rsp+288h+var_268], eax
0x100461df9  mov     r9d, [rsp+288h+var_204]
0x100461e01  lea     r8, aWindowsDDD0; "Windows %d.%d.%d.0"
0x100461e08  mov     edx, 40h ; '@'; BufferCount
0x100461e0d  lea     rcx, [rsp+288h+Buffer]; Buffer
0x100461e15  call    cs:__imp_swprintf_s
0x100461e1b  test    eax, eax
0x100461e1d  jle     short loc_100461E63
0x100461e1f  lea     rcx, [rsp+288h+Buffer]
0x100461e27  or      rax, 0FFFFFFFFFFFFFFFFh
0x100461e2b  inc     rax
0x100461e2e  cmp     [rcx+rax*2], r15w
0x100461e33  jnz     short loc_100461E2B
0x100461e35  mov     edi, 7Fh
0x100461e3a  cmp     rax, rdi
0x100461e3d  cmovb   rdi, rax
0x100461e41  test    rdi, rdi
0x100461e44  jz      short loc_100461E5C
0x100461e46  mov     r8, rdi
0x100461e49  add     r8, r8; Size
0x100461e4c  lea     rdx, [rsp+288h+Buffer]; Src
0x100461e54  mov     rcx, r14; void *
0x100461e57  call    memcpy_0
0x100461e5c  mov     [r14+rdi*2], r15w
0x100461e61  jmp     short loc_100461E9A
0x100461e63  mov     rcx, r15
0x100461e66  mov     rax, r14
0x100461e69  lea     rdx, aUnknown; "Unknown"
0x100461e70  sub     rdx, r14
0x100461e73  mov     edi, 7Fh
0x100461e78  movzx   r8d, word ptr [rdx+rax]
0x100461e7d  test    r8w, r8w
0x100461e81  jz      short loc_100461E92
0x100461e83  mov     [rax], r8w
0x100461e87  inc     rcx
0x100461e8a  add     rax, r13
0x100461e8d  cmp     rcx, rdi
0x100461e90  jb      short loc_100461E78
0x100461e92  mov     [r14+0FEh], r15w
0x100461e9a  lea     rsi, [rbx+120h]
0x100461ea1  test    rsi, rsi
0x100461ea4  jz      short loc_100461F0D
0x100461ea6  lea     rcx, [rsp+288h+SystemInfo]; lpSystemInfo
0x100461eab  call    cs:__imp_GetSystemInfo
0x100461eb1  lea     rax, aUnknown; "Unknown"
0x100461eb8  movzx   ecx, word ptr [rsp+288h+SystemInfo]
0x100461ebd  test    ecx, ecx
0x100461ebf  jz      short loc_100461EDD
0x100461ec1  cmp     ecx, 9
0x100461ec4  jz      short loc_100461ED4
0x100461ec6  cmp     ecx, 0Ch
0x100461ec9  jnz     short loc_100461EE4
0x100461ecb  lea     rax, aArm64; "arm64"
0x100461ed2  jmp     short loc_100461EE4
0x100461ed4  lea     rax, aAmd64; "amd64"
0x100461edb  jmp     short loc_100461EE4
0x100461edd  lea     rax, aX86; "x86"
0x100461ee4  mov     rdx, r15
0x100461ee7  mov     rcx, rsi
0x100461eea  sub     rax, rsi
0x100461eed  movzx   r8d, word ptr [rax+rcx]
0x100461ef2  test    r8w, r8w
0x100461ef6  jz      short loc_100461F08
0x100461ef8  mov     [rcx], r8w
0x100461efc  inc     rdx
0x100461eff  add     rcx, r13
0x100461f02  cmp     rdx, 0Fh
0x100461f06  jb      short loc_100461EED
0x100461f08  mov     [rsi+1Eh], r15w
0x100461f0d  mov     r8, r13; unsigned __int64
0x100461f10  lea     rdx, a1; "1"
0x100461f17  mov     rcx, rbx; this
0x100461f1a  call    ?AppendFilteredField@UserAgent@@QEAAXPEB_S_K@Z; UserAgent::AppendFilteredField(char16_t const *,unsigned __int64)
0x100461f1f  mov     rax, [rbx+340h]
0x100461f26  mov     r13d, 0FFh
0x100461f2c  mov     edi, 7Ch ; '|'
0x100461f31  cmp     rax, r13
0x100461f34  jnb     short loc_100461F45
0x100461f36  mov     [rbx+rax*2+140h], di
0x100461f3e  inc     qword ptr [rbx+340h]
0x100461f45  mov     r8d, 0Ch; unsigned __int64
0x100461f4b  lea     rdx, aMsOdbc; "MS-ODBC"
0x100461f52  mov     rcx, rbx; this
0x100461f55  call    ?AppendFilteredField@UserAgent@@QEAAXPEB_S_K@Z; UserAgent::AppendFilteredField(char16_t const *,unsigned __int64)
0x100461f5a  mov     rax, [rbx+340h]
0x100461f61  cmp     rax, r13
0x100461f64  jnb     short loc_100461F75
0x100461f66  mov     [rbx+rax*2+140h], di
0x100461f6e  inc     qword ptr [rbx+340h]
0x100461f75  xor     edx, edx; Val
0x100461f77  lea     r8d, [rdx+40h]; Size
0x100461f7b  lea     rcx, [rsp+288h+var_E8]; void *
0x100461f83  call    memset_0
0x100461f88  mov     [rsp+288h+var_258], 1
0x100461f90  mov     [rsp+288h+var_260], 2
0x100461f98  mov     [rsp+288h+var_268], 6
0x100461fa0  mov     r9d, 12h
0x100461fa6  lea     r8, aDDDD; "%d.%d.%d.%d"
0x100461fad  lea     edx, [r9+0Eh]; BufferCount
0x100461fb1  lea     rcx, [rsp+288h+var_E8]; Buffer
0x100461fb9  call    cs:__imp_swprintf_s
0x100461fbf  test    eax, eax
0x100461fc1  jns     short loc_100461FCC
0x100461fc3  mov     [rsp+288h+var_E8], r15w
0x100461fcc  mov     r8d, 18h; unsigned __int64
0x100461fd2  lea     rdx, [rsp+288h+var_E8]; char16_t *
0x100461fda  mov     rcx, rbx; this
0x100461fdd  call    ?AppendFilteredField@UserAgent@@QEAAXPEB_S_K@Z; UserAgent::AppendFilteredField(char16_t const *,unsigned __int64)
0x100461fe2  mov     rax, [rbx+340h]
0x100461fe9  cmp     rax, r13
0x100461fec  jnb     short loc_100461FFD
0x100461fee  mov     [rbx+rax*2+140h], di
0x100461ff6  inc     qword ptr [rbx+340h]
0x100461ffd  mov     r8d, 0Ah; unsigned __int64
0x100462003  mov     rdx, rsi; char16_t *
0x100462006  mov     rcx, rbx; this
0x100462009  call    ?AppendFilteredField@UserAgent@@QEAAXPEB_S_K@Z; UserAgent::AppendFilteredField(char16_t const *,unsigned __int64)
0x10046200e  mov     rax, [rbx+340h]
0x100462015  cmp     rax, r13
0x100462018  jnb     short loc_100462029
0x10046201a  mov     [rbx+rax*2+140h], di
0x100462022  inc     qword ptr [rbx+340h]
0x100462029  mov     r8d, 0Ah; unsigned __int64
0x10046202f  mov     rdx, rbx; char16_t *
0x100462032  mov     rcx, rbx; this
0x100462035  call    ?AppendFilteredField@UserAgent@@QEAAXPEB_S_K@Z; UserAgent::AppendFilteredField(char16_t const *,unsigned __int64)
0x10046203a  mov     rax, [rbx+340h]
0x100462041  cmp     rax, r13
0x100462044  jnb     short loc_100462055
0x100462046  mov     [rbx+rax*2+140h], di
0x10046204e  inc     qword ptr [rbx+340h]
0x100462055  mov     esi, 2Ch ; ','
0x10046205a  mov     r8d, esi; unsigned __int64
0x10046205d  mov     rdx, r14; char16_t *
0x100462060  mov     rcx, rbx; this
0x100462063  call    ?AppendFilteredField@UserAgent@@QEAAXPEB_S_K@Z; UserAgent::AppendFilteredField(char16_t const *,unsigned __int64)
0x100462068  mov     rax, [rbx+340h]
0x10046206f  cmp     rax, r13
0x100462072  jnb     short loc_100462083
0x100462074  mov     [rbx+rax*2+140h], di
0x10046207c  inc     qword ptr [rbx+340h]
0x100462083  mov     r8, rsi; unsigned __int64
0x100462086  lea     rdx, aUnknown; "Unknown"
0x10046208d  mov     rcx, rbx; this
0x100462090  call    ?AppendFilteredField@UserAgent@@QEAAXPEB_S_K@Z; UserAgent::AppendFilteredField(char16_t const *,unsigned __int64)
0x100462095  mov     rax, [rbx+340h]
0x10046209c  mov     [rbx+rax*2+140h], r15w
0x1004620a5  jmp     short loc_1004620AC
0x1004620a7  mov     rbx, [rsp+288h+var_248]
0x1004620ac  mov     rax, rbx
0x1004620af  mov     rcx, [rsp+288h+var_28]
0x1004620b7  xor     rcx, rsp; StackCookie
0x1004620ba  call    __security_check_cookie
0x1004620bf  lea     r11, [rsp+288h+var_18]
0x1004620c7  mov     rbx, [r11+28h]
0x1004620cb  mov     rsi, [r11+30h]
0x1004620cf  mov     rdi, [r11+38h]
0x1004620d3  mov     rsp, r11
0x1004620d6  pop     r15
0x1004620d8  pop     r14
0x1004620da  pop     r13
0x1004620dc  retn
```
