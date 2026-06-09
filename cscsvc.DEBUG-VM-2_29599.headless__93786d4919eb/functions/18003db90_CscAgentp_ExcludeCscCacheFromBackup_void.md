# CscAgentp_ExcludeCscCacheFromBackup(void)

- ea: `0x18003db90`
- end: `0x18003ddce`
- name: `?CscAgentp_ExcludeCscCacheFromBackup@@YAJXZ`
- size: `574`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18003ce68`

## callees

- `0x18000ca48`
- `0x18000d640`
- `0x18001a0c0`
- `0x18001b4e0`
- `0x18001ba60`
- `0x180029ee0`
- `0x180036394`
- `0x180039610`
- `0x18003c354`
- `0x18003db90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003dd5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003dd5b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dd0c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dd0c`

## string_xrefs

- `0x18003dd05`: `Offline Files Cache`

## pseudocode

```c
__int64 CscAgentp_ExcludeCscCacheFromBackup(void)
{
  signed int CacheLocation; // ebx
  void *v1; // rdx
  unsigned __int16 *v2; // r9
  _WORD *v3; // rdx
  _WORD *v4; // r8
  __int64 v5; // rcx
  const unsigned __int16 *ConstBuffer; // rax
  const BYTE *v7; // rdx
  LSTATUS v8; // eax
  unsigned int lpData; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v11; // [rsp+30h] [rbp-D0h]
  unsigned int *v12; // [rsp+40h] [rbp-C0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v14; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v15[260]; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+268h] [rbp+168h]
  _WORD *v17; // [rsp+270h] [rbp+170h]
  unsigned int v18[2]; // [rsp+278h] [rbp+178h]
  _WORD *v19; // [rsp+280h] [rbp+180h]
  __int64 v20; // [rsp+288h] [rbp+188h]
  __int64 v21; // [rsp+290h] [rbp+190h]

  v14 = 0;
  CacheLocation = CscLib_GetCacheLocation(&v14);
  if ( CacheLocation >= 0 )
  {
    *(_QWORD *)v18 = v15;
    v20 = 520;
    v19 = v15;
    v21 = 520;
    v17 = v15;
    v15[0] = 0;
    v16 = 34078720;
    CacheLocation = CPath::Copy((CPath *)v15, v14);
    if ( CacheLocation >= 0 )
    {
      CacheLocation = CPath::Append((CPath *)v15, L"* /s_");
      if ( CacheLocation >= 0 )
      {
        v3 = v17;
        v4 = v17;
        if ( *(_WORD **)v18 != v19 )
        {
          v3 = *(_WORD **)v18;
          v4 = *(_WORD **)v18;
        }
        v5 = -1;
        do
          ++v5;
        while ( v3[v5] );
        v4[v5 - 1] = 0;
        hKey = 0;
        CacheLocation = CscReg_CreateKeyEx(
                          HKEY_LOCAL_MACHINE,
                          L"System\\CurrentControlSet\\Control\\BackupRestore\\FilesNotToBackup",
                          (unsigned int)v4,
                          v2,
                          lpData,
                          0x20006u,
                          v11,
                          &hKey,
                          v12);
        if ( CacheLocation < 0 )
        {
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50,
              WPP_ef399ae69b0439092b78fa9bd8d7e9cf_Traceguids,
              (unsigned int)CacheLocation);
          }
        }
        else
        {
          ConstBuffer = CPath::_GetConstBuffer((CPath *)v15);
          v7 = (const BYTE *)ConstBuffer;
          if ( !*ConstBuffer )
            goto LABEL_11;
          do
          {
            do
              ++ConstBuffer;
            while ( *ConstBuffer );
LABEL_11:
            ++ConstBuffer;
          }
          while ( *ConstBuffer );
          v8 = RegSetValueExW(
                 hKey,
                 L"Offline Files Cache",
                 0,
                 7u,
                 v7,
                 2 * (((char *)ConstBuffer - (char *)v7) >> 1) + 2);
          CacheLocation = v8;
          if ( v8 > 0 )
            CacheLocation = (unsigned __int16)v8 | 0x80070000;
          if ( CacheLocation < 0
            && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              49,
              WPP_ef399ae69b0439092b78fa9bd8d7e9cf_Traceguids,
              (unsigned int)CacheLocation);
          }
          RegCloseKey(hKey);
        }
      }
    }
    CscUtil_HeapFree(v14, v1);
    CPath::~CPath((CPath *)v15);
  }
  return (unsigned int)CacheLocation;
}

```

## disassembly

```asm
0x18003db90  mov     [rsp-8+arg_0], rbx
0x18003db95  mov     [rsp-8+arg_8], rdi
0x18003db9a  push    rbp
0x18003db9b  lea     rbp, [rsp-1B0h]
0x18003dba3  sub     rsp, 2B0h
0x18003dbaa  mov     rax, cs:__security_cookie
0x18003dbb1  xor     rax, rsp
0x18003dbb4  mov     [rbp+1B0h+var_10], rax
0x18003dbbb  xor     edi, edi
0x18003dbbd  lea     rcx, [rsp+2B0h+var_258]; unsigned __int16 **
0x18003dbc2  mov     [rsp+2B0h+var_258], rdi
0x18003dbc7  call    ?CscLib_GetCacheLocation@@YAJPEAPEAG@Z; CscLib_GetCacheLocation(ushort * *)
0x18003dbcc  mov     ebx, eax
0x18003dbce  test    eax, eax
0x18003dbd0  js      loc_18003DDA8
0x18003dbd6  mov     rdx, [rsp+2B0h+var_258]; unsigned __int16 *
0x18003dbdb  lea     rax, [rsp+2B0h+var_250]
0x18003dbe0  mov     qword ptr [rbp+1B0h+var_38], rax
0x18003dbe7  mov     ecx, 208h
0x18003dbec  lea     rax, [rsp+2B0h+var_250]
0x18003dbf1  mov     [rbp+1B0h+var_28], rcx
0x18003dbf8  mov     [rbp+1B0h+var_30], rax
0x18003dbff  lea     rax, [rsp+2B0h+var_250]
0x18003dc04  mov     [rbp+1B0h+var_20], rcx
0x18003dc0b  lea     rcx, [rsp+2B0h+var_250]; this
0x18003dc10  mov     [rbp+1B0h+var_40], rax
0x18003dc17  mov     [rsp+2B0h+var_250], di
0x18003dc1c  mov     [rbp+1B0h+var_48], 2080000h
0x18003dc26  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x18003dc2b  mov     ebx, eax
0x18003dc2d  test    eax, eax
0x18003dc2f  js      loc_18003DD94
0x18003dc35  lea     rdx, aS; "* /s_"
0x18003dc3c  lea     rcx, [rsp+2B0h+var_250]; this
0x18003dc41  call    ?Append@CPath@@QEAAJPEBG@Z; CPath::Append(ushort const *)
0x18003dc46  mov     ebx, eax
0x18003dc48  test    eax, eax
0x18003dc4a  js      loc_18003DD94
0x18003dc50  mov     rax, qword ptr [rbp+1B0h+var_38]
0x18003dc57  cmp     rax, [rbp+1B0h+var_30]
0x18003dc5e  mov     rdx, [rbp+1B0h+var_40]
0x18003dc65  mov     r8, rdx
0x18003dc68  cmovnz  rdx, rax
0x18003dc6c  cmovnz  r8, rax; unsigned int
0x18003dc70  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003dc74  inc     rcx
0x18003dc77  cmp     [rdx+rcx*2], di
0x18003dc7b  jnz     short loc_18003DC74
0x18003dc7d  mov     [r8+rcx*2-2], di
0x18003dc83  lea     rax, [rsp+2B0h+hKey]
0x18003dc88  mov     [rsp+2B0h+var_278], rax; PHKEY
0x18003dc8d  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Bac"...
0x18003dc94  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18003dc9b  mov     [rsp+2B0h+cbData], 20006h; REGSAM
0x18003dca3  mov     [rsp+2B0h+hKey], rdi
0x18003dca8  call    ?CscReg_CreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; CscReg_CreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18003dcad  mov     ebx, eax
0x18003dcaf  test    eax, eax
0x18003dcb1  js      loc_18003DD63
0x18003dcb7  lea     rcx, [rsp+2B0h+var_250]; this
0x18003dcbc  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18003dcc1  mov     rdx, rax
0x18003dcc4  movzx   ecx, word ptr [rax]
0x18003dcc7  test    cx, cx
0x18003dcca  jz      short loc_18003DCD5
0x18003dccc  add     rax, 2
0x18003dcd0  cmp     [rax], di
0x18003dcd3  jnz     short loc_18003DCCC
0x18003dcd5  add     rax, 2
0x18003dcd9  movzx   ecx, word ptr [rax]
0x18003dcdc  test    cx, cx
0x18003dcdf  jnz     short loc_18003DCCC
0x18003dce1  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003dce6  sub     rax, rdx
0x18003dce9  sar     rax, 1
0x18003dcec  mov     r9d, 7; dwType
0x18003dcf2  xor     r8d, r8d; Reserved
0x18003dcf5  lea     eax, ds:2[rax*2]
0x18003dcfc  mov     [rsp+2B0h+cbData], eax; cbData
0x18003dd00  mov     [rsp+2B0h+lpData], rdx; lpData
0x18003dd05  lea     rdx, ValueName; "Offline Files Cache"
0x18003dd0c  call    cs:__imp_RegSetValueExW
0x18003dd12  mov     ebx, eax
0x18003dd14  test    eax, eax
0x18003dd16  jle     short loc_18003DD21
0x18003dd18  movzx   ebx, ax
0x18003dd1b  or      ebx, 80070000h
0x18003dd21  test    ebx, ebx
0x18003dd23  jns     short loc_18003DD56
0x18003dd25  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dd2c  lea     rax, WPP_GLOBAL_Control
0x18003dd33  cmp     rcx, rax
0x18003dd36  jz      short loc_18003DD56
0x18003dd38  test    byte ptr [rcx+1Ch], 2
0x18003dd3c  jz      short loc_18003DD56
0x18003dd3e  mov     rcx, [rcx+10h]
0x18003dd42  lea     r8, WPP_ef399ae69b0439092b78fa9bd8d7e9cf_Traceguids
0x18003dd49  mov     edx, 31h ; '1'
0x18003dd4e  mov     r9d, ebx
0x18003dd51  call    WPP_SF_d
0x18003dd56  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003dd5b  call    cs:__imp_RegCloseKey
0x18003dd61  jmp     short loc_18003DD94
0x18003dd63  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dd6a  lea     rax, WPP_GLOBAL_Control
0x18003dd71  cmp     rcx, rax
0x18003dd74  jz      short loc_18003DD94
0x18003dd76  test    byte ptr [rcx+1Ch], 2
0x18003dd7a  jz      short loc_18003DD94
0x18003dd7c  mov     rcx, [rcx+10h]
0x18003dd80  lea     r8, WPP_ef399ae69b0439092b78fa9bd8d7e9cf_Traceguids
0x18003dd87  mov     edx, 32h ; '2'
0x18003dd8c  mov     r9d, ebx
0x18003dd8f  call    WPP_SF_d
0x18003dd94  mov     rcx, [rsp+2B0h+var_258]; lpMem
0x18003dd99  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18003dd9e  lea     rcx, [rsp+2B0h+var_250]; this
0x18003dda3  call    ??1CPath@@QEAA@XZ; CPath::~CPath(void)
0x18003dda8  mov     eax, ebx
0x18003ddaa  mov     rcx, [rbp+1B0h+var_10]
0x18003ddb1  xor     rcx, rsp; StackCookie
0x18003ddb4  call    __security_check_cookie
0x18003ddb9  lea     r11, [rsp+2B0h+var_s0]
0x18003ddc1  mov     rbx, [r11+10h]
0x18003ddc5  mov     rdi, [r11+18h]
0x18003ddc9  mov     rsp, r11
0x18003ddcc  pop     rbp
0x18003ddcd  retn
```
