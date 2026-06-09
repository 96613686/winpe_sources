# RtlpGetDeviceFamilyInfoEnum

- ea: `0x1800012e0`
- end: `0x1800015a3`
- name: `RtlpGetDeviceFamilyInfoEnum`
- size: `707`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800011e0`
- `0x1800012d0`

## callees

- `0x1800012e0`
- `0x1800015ac`
- `0x1800028a0`
- `0x18012d320`
- `0x18015ecc0`
- `0x18015ed20`
- `0x1801616d0`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x1800013d8`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\OEM`
- `0x1800014b4`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion`

## pseudocode

```c
void __fastcall RtlpGetDeviceFamilyInfoEnum(_QWORD *a1, _DWORD *a2, _DWORD *a3)
{
  size_t v6; // rax
  size_t v7; // rax
  __int64 v8; // r14
  size_t v9; // rax
  __int64 v10; // [rsp+38h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v12; // [rsp+48h] [rbp-C0h] BYREF
  const wchar_t *v13; // [rsp+50h] [rbp-B8h]
  int v14; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v16; // [rsp+70h] [rbp-98h]
  __int128 v17; // [rsp+80h] [rbp-88h]
  _DWORD v18[72]; // [rsp+98h] [rbp-70h] BYREF

  if ( a1 )
  {
    memset_thunk_772440563353939046(v18, 0, 0x11Cu);
    Handle = 0;
    LODWORD(v10) = 0;
    v15 = 0x30u;
    v13 = L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion";
    v8 = 0;
    v16 = 0;
    v12 = 0;
    v17 = 0;
    v9 = 2 * wcslen(L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion");
    DWORD2(v16) = 64;
    if ( v9 >= 0xFFFE )
      LOWORD(v9) = -4;
    LOWORD(v12) = v9;
    WORD1(v12) = v9 + 2;
    *(_QWORD *)&v16 = &v12;
    v17 = 0;
    if ( (int)NtOpenKey(&Handle, 131353, &v15) >= 0 )
    {
      if ( (int)ReadUlongFromKey(Handle, L"UBR", &v10) >= 0 )
        v8 = (unsigned int)v10;
      NtClose(Handle);
    }
    v18[0] = 284;
    RtlGetVersion(v18);
    *a1 = v8 + ((v18[3] + ((v18[2] + ((unsigned __int64)v18[1] << 16)) << 16)) << 16);
  }
  if ( a2 )
  {
    LODWORD(Handle) = 0;
    v13 = L"Kernel-OneCore-DeviceFamilyID";
    v14 = 0;
    LODWORD(v10) = 3;
    v12 = 0;
    v6 = 2 * wcslen(L"Kernel-OneCore-DeviceFamilyID");
    if ( v6 >= 0xFFFE )
      LOWORD(v6) = -4;
    LOWORD(v12) = v6;
    WORD1(v12) = v6 + 2;
    ZwQueryLicenseValue(&v12, &Handle, &v10, 4, &v14);
    *a2 = v10;
  }
  if ( a3 )
  {
    Handle = 0;
    LODWORD(v10) = 0;
    v15 = 0;
    v13 = L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\OEM";
    v16 = 0;
    *a3 = 0;
    v17 = 0;
    v12 = 0;
    v7 = 2 * wcslen(L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\OEM");
    LODWORD(v15) = 48;
    *((_QWORD *)&v15 + 1) = 0;
    DWORD2(v16) = 64;
    if ( v7 >= 0xFFFE )
      LOWORD(v7) = -4;
    LOWORD(v12) = v7;
    WORD1(v12) = v7 + 2;
    *(_QWORD *)&v16 = &v12;
    v17 = 0;
    if ( (int)NtOpenKey(&Handle, 131353, &v15) >= 0 )
    {
      if ( (int)ReadUlongFromKey(Handle, L"DeviceForm", &v10) >= 0 )
        *a3 = v10;
      NtClose(Handle);
    }
  }
}

```

## disassembly

```asm
0x1800012e0  mov     r11, rsp
0x1800012e3  push    rbp
0x1800012e4  push    rdi
0x1800012e5  push    r12
0x1800012e7  push    r15
0x1800012e9  lea     rbp, [r11-0F8h]
0x1800012f0  sub     rsp, 1D8h
0x1800012f7  mov     rax, cs:__security_cookie
0x1800012fe  xor     rax, rsp
0x180001301  mov     [rbp+0F0h+var_40], rax
0x180001308  mov     [r11-28h], rbx
0x18000130c  xor     r15d, r15d
0x18000130f  mov     [r11-30h], rsi
0x180001313  mov     rdi, r8
0x180001316  mov     rbx, rdx
0x180001319  mov     rsi, rcx
0x18000131c  mov     r12d, 0FFFCh
0x180001322  test    rcx, rcx
0x180001325  jnz     loc_180001493
0x18000132b  mov     rsi, [rsp+1F0h+var_28]
0x180001333  test    rbx, rbx
0x180001336  jz      short loc_1800013A5
0x180001338  lea     rcx, aKernelOnecoreD; "Kernel-OneCore-DeviceFamilyID"
0x18000133f  mov     dword ptr [rsp+1F0h+Handle], r15d
0x180001344  mov     [rsp+1F0h+var_1A8], rcx
0x180001349  mov     dword ptr [rsp+1F0h+var_1A0], r15d
0x18000134e  mov     dword ptr [rsp+1F0h+var_1C0], 3
0x180001356  mov     [rsp+1F0h+var_1B0], r15
0x18000135b  call    wcslen
0x180001360  add     rax, rax
0x180001363  lea     r8, [rsp+1F0h+var_1C0]
0x180001368  cmp     rax, 0FFFEh
0x18000136e  lea     rdx, [rsp+1F0h+Handle]
0x180001373  mov     r9d, 4
0x180001379  lea     rcx, [rsp+1F0h+var_1B0]
0x18000137e  cmovnb  rax, r12
0x180001382  mov     word ptr [rsp+1F0h+var_1B0], ax
0x180001387  add     ax, 2
0x18000138b  mov     word ptr [rsp+1F0h+var_1B0+2], ax
0x180001390  lea     rax, [rsp+1F0h+var_1A0]
0x180001395  mov     [rsp+20h], rax
0x18000139a  call    ZwQueryLicenseValue
0x18000139f  mov     eax, dword ptr [rsp+1F0h+var_1C0]
0x1800013a3  mov     [rbx], eax
0x1800013a5  mov     rbx, [rsp+1D0h]
0x1800013ad  test    rdi, rdi
0x1800013b0  jnz     short loc_1800013D0
0x1800013b2  mov     rcx, [rbp+0F0h+var_40]
0x1800013b9  xor     rcx, rsp; StackCookie
0x1800013bc  call    __security_check_cookie
0x1800013c1  add     rsp, 1D8h
0x1800013c8  pop     r15
0x1800013ca  pop     r12
0x1800013cc  pop     rdi
0x1800013cd  pop     rbp
0x1800013ce  retn
0x1800013d0  xorps   xmm0, xmm0
0x1800013d3  mov     [rsp+1F0h+Handle], r15
0x1800013d8  lea     rcx, aRegistryMachin_12; "\\Registry\\Machine\\Software\\Microsof"...
0x1800013df  mov     dword ptr [rsp+1F0h+var_1C0], r15d
0x1800013e4  movups  [rsp+1F0h+var_1A0+8], xmm0
0x1800013e9  mov     [rsp+1F0h+var_1A8], rcx
0x1800013ee  movups  [rsp+1F0h+var_190+8], xmm0
0x1800013f3  mov     [rdi], r15d
0x1800013f6  movups  xmmword ptr [rsp+1F0h+var_180+8], xmm0
0x1800013fb  mov     [rsp+1F0h+var_1B0], r15
0x180001400  call    wcslen
0x180001405  add     rax, rax
0x180001408  mov     dword ptr [rsp+1F0h+var_1A0+8], 30h ; '0'
0x180001410  cmp     rax, 0FFFEh
0x180001416  mov     qword ptr [rsp+1F0h+var_190], r15
0x18000141b  xorps   xmm0, xmm0
0x18000141e  mov     dword ptr [rsp+1F0h+var_180], 40h ; '@'
0x180001426  cmovnb  rax, r12
0x18000142a  lea     r8, [rsp+1F0h+var_1A0+8]
0x18000142f  mov     word ptr [rsp+1F0h+var_1B0], ax
0x180001434  lea     rcx, [rsp+1F0h+Handle]
0x180001439  add     ax, 2
0x18000143d  mov     edx, 20119h
0x180001442  mov     word ptr [rsp+1F0h+var_1B0+2], ax
0x180001447  lea     rax, [rsp+1F0h+var_1B0]
0x18000144c  mov     qword ptr [rsp+1F0h+var_190+8], rax
0x180001451  movdqu  xmmword ptr [rsp+1F0h+var_180+8], xmm0
0x180001457  call    NtOpenKey
0x18000145c  test    eax, eax
0x18000145e  js      loc_1800013B2
0x180001464  mov     rcx, [rsp+1F0h+Handle]
0x180001469  lea     r8, [rsp+1F0h+var_1C0]
0x18000146e  lea     rdx, aDeviceform; "DeviceForm"
0x180001475  call    ReadUlongFromKey
0x18000147a  test    eax, eax
0x18000147c  js      short loc_180001484
0x18000147e  mov     eax, dword ptr [rsp+1F0h+var_1C0]
0x180001482  mov     [rdi], eax
0x180001484  mov     rcx, [rsp+1F0h+Handle]; Handle
0x180001489  call    NtClose
0x18000148e  jmp     loc_1800013B2
0x180001493  xor     edx, edx; Val
0x180001495  mov     [rsp+1F0h+var_30], r14
0x18000149d  mov     r8d, 11Ch; Size
0x1800014a3  lea     rcx, [rbp+0F0h+var_160]; void *
0x1800014a7  call    memset$thunk$772440563353939046
0x1800014ac  xorps   xmm0, xmm0
0x1800014af  mov     [rsp+1F0h+Handle], r15
0x1800014b4  lea     rcx, aRegistryMachin_26; "\\Registry\\Machine\\Software\\Microsof"...
0x1800014bb  mov     dword ptr [rsp+1F0h+var_1C0], r15d
0x1800014c0  movups  [rsp+1F0h+var_1A0+8], xmm0
0x1800014c5  mov     [rsp+1F0h+var_1A8], rcx
0x1800014ca  mov     r14, r15
0x1800014cd  movups  [rsp+1F0h+var_190+8], xmm0
0x1800014d2  mov     [rsp+1F0h+var_1B0], r15
0x1800014d7  movups  xmmword ptr [rsp+1F0h+var_180+8], xmm0
0x1800014dc  call    wcslen
0x1800014e1  add     rax, rax
0x1800014e4  mov     dword ptr [rsp+1F0h+var_1A0+8], 30h ; '0'
0x1800014ec  cmp     rax, 0FFFEh
0x1800014f2  mov     qword ptr [rsp+1F0h+var_190], r15
0x1800014f7  xorps   xmm0, xmm0
0x1800014fa  mov     dword ptr [rsp+1F0h+var_180], 40h ; '@'
0x180001502  cmovnb  rax, r12
0x180001506  lea     r8, [rsp+1F0h+var_1A0+8]
0x18000150b  mov     word ptr [rsp+1F0h+var_1B0], ax
0x180001510  lea     rcx, [rsp+1F0h+Handle]
0x180001515  add     ax, 2
0x180001519  mov     edx, 20119h
0x18000151e  mov     word ptr [rsp+1F0h+var_1B0+2], ax
0x180001523  lea     rax, [rsp+1F0h+var_1B0]
0x180001528  mov     qword ptr [rsp+1F0h+var_190+8], rax
0x18000152d  movdqu  xmmword ptr [rsp+1F0h+var_180+8], xmm0
0x180001533  call    NtOpenKey
0x180001538  test    eax, eax
0x18000153a  js      short loc_180001565
0x18000153c  mov     rcx, [rsp+1F0h+Handle]
0x180001541  lea     r8, [rsp+1F0h+var_1C0]
0x180001546  lea     rdx, aUbr; "UBR"
0x18000154d  call    ReadUlongFromKey
0x180001552  test    eax, eax
0x180001554  js      short loc_18000155B
0x180001556  mov     r14d, dword ptr [rsp+1F0h+var_1C0]
0x18000155b  mov     rcx, [rsp+1F0h+Handle]; Handle
0x180001560  call    NtClose
0x180001565  lea     rcx, [rbp+0F0h+var_160]
0x180001569  mov     [rbp+0F0h+var_160], 11Ch
0x180001570  call    RtlGetVersion
0x180001575  mov     eax, [rbp+0F0h+var_158]
0x180001578  mov     ecx, [rbp+0F0h+var_15C]
0x18000157b  shl     rcx, 10h
0x18000157f  add     rcx, rax
0x180001582  mov     eax, [rbp+0F0h+var_154]
0x180001585  shl     rcx, 10h
0x180001589  add     rcx, rax
0x18000158c  shl     rcx, 10h
0x180001590  add     rcx, r14
0x180001593  mov     r14, [rsp+1F0h+var_30]
0x18000159b  mov     [rsi], rcx
0x18000159e  jmp     loc_18000132B
```
