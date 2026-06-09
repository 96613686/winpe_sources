# SetDisplayStateFromCalibrationData(IDxva2Wrapper *,HMONITOR__ *,CalibrationData *)

- ea: `0x180019a3c`
- end: `0x180019c3f`
- name: `?SetDisplayStateFromCalibrationData@@YAJPEAVIDxva2Wrapper@@PEAUHMONITOR__@@PEAUCalibrationData@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(struct IDxva2Wrapper *, HMONITOR, struct CalibrationData *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180047f20`

## callees

- `0x180019a3c`
- `0x180019c48`
- `0x18002e5f0`
- `0x18002f2f4`
- `0x18005bd80`
- `0x180084010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180019bdc`
- `ntdll!EtwEventWrite` at `0x180019c1b`
- `ntdll!EtwEventWrite` at `0x180019bdc`
- `ntdll!EtwEventWrite` at `0x180019c1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b56`

## pseudocode

```c
signed int __fastcall SetDisplayStateFromCalibrationData(
        struct IDxva2Wrapper *a1,
        HMONITOR a2,
        struct CalibrationData *a3)
{
  unsigned int (__fastcall **v6)(struct IDxva2Wrapper *, HMONITOR, int *); // rax
  signed int result; // eax
  signed int LastError; // eax
  int v9; // [rsp+30h] [rbp-D0h] BYREF
  int v10; // [rsp+34h] [rbp-CCh] BYREF
  int v11; // [rsp+38h] [rbp-C8h] BYREF
  int v12; // [rsp+3Ch] [rbp-C4h] BYREF
  void *v13[34]; // [rsp+40h] [rbp-C0h] BYREF
  int *v14; // [rsp+150h] [rbp+50h] BYREF
  __int64 v15; // [rsp+158h] [rbp+58h]
  int *v16; // [rsp+160h] [rbp+60h]
  __int64 v17; // [rsp+168h] [rbp+68h]

  v9 = 0;
  v12 = 0;
  v11 = 0;
  if ( !a2 || !a3 )
  {
    result = -2147024809;
LABEL_23:
    v9 = result;
LABEL_24:
    if ( result >= 0 )
      return result;
    goto LABEL_25;
  }
  v6 = *(unsigned int (__fastcall ***)(struct IDxva2Wrapper *, HMONITOR, int *))a1;
  v10 = 0;
  if ( !(*v6)(a1, a2, &v10) )
  {
LABEL_4:
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    goto LABEL_23;
  }
  if ( v10 == 1 )
  {
    if ( *((_QWORD *)a3 + 1) )
    {
      memset_0(v13, 0, 0x108u);
      if ( !(*(unsigned int (__fastcall **)(struct IDxva2Wrapper *, HMONITOR, __int64, void **))(*(_QWORD *)a1 + 8LL))(
              a1,
              a2,
              1,
              v13) )
        goto LABEL_4;
      v9 = ApplyMonitorConfiguration(a1, v13[0], *((const struct MonitorConfiguration **)a3 + 1));
      if ( (*(unsigned int (__fastcall **)(struct IDxva2Wrapper *, __int64, void **))(*(_QWORD *)a1 + 16LL))(a1, 1, v13) )
      {
        LastError = v9;
      }
      else
      {
        if ( v9 < 0 )
          goto LABEL_25;
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v9 = LastError;
      }
      if ( LastError < 0 )
        goto LABEL_25;
      v12 = 1;
    }
    if ( *(_QWORD *)a3 )
    {
      v9 = ApplyAdapterConfiguration(
             a2,
             *(struct AdapterGammaConfiguration **)a3,
             *((float *)a3 + 8),
             *((float *)a3 + 9));
      if ( v9 < 0 )
        goto LABEL_25;
      v11 = 1;
    }
    v14 = &v11;
    v15 = 4;
    v16 = &v12;
    v17 = 4;
    EtwEventWrite(g_etwHandle, APPLYING_CALIBRATION_ADJUSTMENTS, 2, &v14);
    result = v9;
    goto LABEL_24;
  }
  v9 = -2147467259;
LABEL_25:
  v14 = &v9;
  v15 = 4;
  EtwEventWrite(g_etwHandle, CALIBRATION_APPLYING_DATA_FAILED, 1, &v14);
  return v9;
}

```

## disassembly

```asm
0x180019a3c  push    rbp
0x180019a3e  push    rbx
0x180019a3f  push    rsi
0x180019a40  push    rdi
0x180019a41  push    r15
0x180019a43  lea     rbp, [rsp-80h]
0x180019a48  sub     rsp, 180h
0x180019a4f  mov     rax, cs:__security_cookie
0x180019a56  xor     rax, rsp
0x180019a59  mov     [rbp+0A0h+var_30], rax
0x180019a5d  mov     [rsp+1A0h+var_170], 0
0x180019a65  mov     rbx, r8
0x180019a68  mov     [rsp+1A0h+var_164], 0
0x180019a70  mov     rsi, rdx
0x180019a73  mov     [rsp+1A0h+var_168], 0
0x180019a7b  mov     rdi, rcx
0x180019a7e  mov     r15d, 1
0x180019a84  test    rdx, rdx
0x180019a87  jz      loc_180019BE8
0x180019a8d  test    rbx, rbx
0x180019a90  jz      loc_180019BE8
0x180019a96  mov     rax, [rcx]
0x180019a99  lea     r8, [rsp+1A0h+var_16C]
0x180019a9e  mov     [rsp+1A0h+var_16C], 0
0x180019aa6  mov     rax, [rax]
0x180019aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019aae  test    eax, eax
0x180019ab0  jnz     short loc_180019ACD
0x180019ab2  call    cs:__imp_GetLastError
0x180019ab8  test    eax, eax
0x180019aba  jle     loc_180019BED
0x180019ac0  movzx   eax, ax
0x180019ac3  or      eax, 80070000h
0x180019ac8  jmp     loc_180019BED
0x180019acd  cmp     [rsp+1A0h+var_16C], r15d
0x180019ad2  jz      short loc_180019AE1
0x180019ad4  mov     [rsp+1A0h+var_170], 80004005h
0x180019adc  jmp     loc_180019BF5
0x180019ae1  cmp     qword ptr [rbx+8], 0
0x180019ae6  jz      loc_180019B7B
0x180019aec  xor     edx, edx; Val
0x180019aee  lea     rcx, [rsp+1A0h+var_160]; void *
0x180019af3  mov     r8d, 108h; Size
0x180019af9  call    memset_0
0x180019afe  mov     rax, [rdi]
0x180019b01  lea     r9, [rsp+1A0h+var_160]
0x180019b06  mov     r8d, r15d
0x180019b09  mov     rdx, rsi
0x180019b0c  mov     rcx, rdi
0x180019b0f  mov     rax, [rax+8]
0x180019b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b18  test    eax, eax
0x180019b1a  jz      short loc_180019AB2
0x180019b1c  mov     r8, [rbx+8]; struct MonitorConfiguration *
0x180019b20  mov     rcx, rdi; struct IDxva2Wrapper *
0x180019b23  mov     rdx, [rsp+1A0h+var_160]; void *
0x180019b28  call    ?ApplyMonitorConfiguration@@YAJPEAVIDxva2Wrapper@@PEAXPEBUMonitorConfiguration@@@Z; ApplyMonitorConfiguration(IDxva2Wrapper *,void *,MonitorConfiguration const *)
0x180019b2d  mov     [rsp+1A0h+var_170], eax
0x180019b31  lea     r8, [rsp+1A0h+var_160]
0x180019b36  mov     rax, [rdi]
0x180019b39  mov     edx, r15d
0x180019b3c  mov     rcx, rdi
0x180019b3f  mov     rax, [rax+10h]
0x180019b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b48  test    eax, eax
0x180019b4a  jnz     short loc_180019B6E
0x180019b4c  cmp     [rsp+1A0h+var_170], eax
0x180019b50  jl      loc_180019BF5
0x180019b56  call    cs:__imp_GetLastError
0x180019b5c  test    eax, eax
0x180019b5e  jle     short loc_180019B68
0x180019b60  movzx   eax, ax
0x180019b63  or      eax, 80070000h
0x180019b68  mov     [rsp+1A0h+var_170], eax
0x180019b6c  jmp     short loc_180019B72
0x180019b6e  mov     eax, [rsp+1A0h+var_170]
0x180019b72  test    eax, eax
0x180019b74  js      short loc_180019BF5
0x180019b76  mov     [rsp+1A0h+var_164], r15d
0x180019b7b  mov     rdx, [rbx]; struct AdapterGammaConfiguration *
0x180019b7e  test    rdx, rdx
0x180019b81  jz      short loc_180019BA2
0x180019b83  movss   xmm3, dword ptr [rbx+24h]; float
0x180019b88  mov     rcx, rsi; HMONITOR
0x180019b8b  movss   xmm2, dword ptr [rbx+20h]; float
0x180019b90  call    ?ApplyAdapterConfiguration@@YAJPEAUHMONITOR__@@PEAUAdapterGammaConfiguration@@MM@Z; ApplyAdapterConfiguration(HMONITOR__ *,AdapterGammaConfiguration *,float,float)
0x180019b95  mov     [rsp+1A0h+var_170], eax
0x180019b99  test    eax, eax
0x180019b9b  js      short loc_180019BF5
0x180019b9d  mov     [rsp+1A0h+var_168], r15d
0x180019ba2  mov     rcx, cs:g_etwHandle
0x180019ba9  lea     rax, [rsp+1A0h+var_168]
0x180019bae  mov     [rbp+0A0h+var_50], rax
0x180019bb2  lea     r9, [rbp+0A0h+var_50]
0x180019bb6  lea     rax, [rsp+1A0h+var_164]
0x180019bbb  mov     [rbp+0A0h+var_48], 4
0x180019bc3  mov     r8d, 2
0x180019bc9  mov     [rbp+0A0h+var_40], rax
0x180019bcd  lea     rdx, APPLYING_CALIBRATION_ADJUSTMENTS
0x180019bd4  mov     [rbp+0A0h+var_38], 4
0x180019bdc  call    cs:__imp_EtwEventWrite
0x180019be2  mov     eax, [rsp+1A0h+var_170]
0x180019be6  jmp     short loc_180019BF1
0x180019be8  mov     eax, 80070057h
0x180019bed  mov     [rsp+1A0h+var_170], eax
0x180019bf1  test    eax, eax
0x180019bf3  jns     short loc_180019C25
0x180019bf5  mov     rcx, cs:g_etwHandle
0x180019bfc  lea     rax, [rsp+1A0h+var_170]
0x180019c01  lea     r9, [rbp+0A0h+var_50]
0x180019c05  mov     [rbp+0A0h+var_50], rax
0x180019c09  mov     r8d, r15d
0x180019c0c  mov     [rbp+0A0h+var_48], 4
0x180019c14  lea     rdx, CALIBRATION_APPLYING_DATA_FAILED
0x180019c1b  call    cs:__imp_EtwEventWrite
0x180019c21  mov     eax, [rsp+1A0h+var_170]
0x180019c25  mov     rcx, [rbp+0A0h+var_30]
0x180019c29  xor     rcx, rsp; StackCookie
0x180019c2c  call    __security_check_cookie
0x180019c31  add     rsp, 180h
0x180019c38  pop     r15
0x180019c3a  pop     rdi
0x180019c3b  pop     rsi
0x180019c3c  pop     rbx
0x180019c3d  pop     rbp
0x180019c3e  retn
```
