# GetAllDeviceIds

- ea: `0x180006644`
- end: `0x180006845`
- name: `GetAllDeviceIds`
- size: `513`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006dc4`

## callees

- `0x180006644`
- `0x180008dfe`
- `0x180008e30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800066b8`
- `KERNEL32!GetLastError` at `0x18000675a`
- `KERNEL32!GetLastError` at `0x180006789`
- `KERNEL32!GetLastError` at `0x1800066b8`
- `KERNEL32!GetLastError` at `0x18000675a`
- `KERNEL32!GetLastError` at `0x180006789`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000679a`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000679a`
- `SETUPAPI!pSetupStringTableAddString` at `0x180006811`
- `SETUPAPI!pSetupStringTableAddString` at `0x180006811`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180006750`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180006750`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x1800066a9`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x1800066a9`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x1800066ed`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180006778`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x1800066ed`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180006778`

## pseudocode

```c
__int64 __fastcall GetAllDeviceIds(__int64 a1)
{
  HDEVINFO ClassDevs; // rax
  void *v3; // rsi
  DWORD v4; // ebx
  DWORD v5; // r15d
  BOOL v6; // eax
  int v7; // r14d
  const DEVPROPKEY *v8; // r8
  DWORD LastError; // eax
  DWORD v10; // eax
  unsigned __int64 v12; // rax
  BYTE *i; // rdi
  __int64 v14; // rax
  DEVPROPTYPE PropertyType; // [rsp+40h] [rbp-C0h] BYREF
  DWORD RequiredSize; // [rsp+44h] [rbp-BCh] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v18[2]; // [rsp+6Ch] [rbp-94h]
  BYTE PropertyBuffer[2048]; // [rsp+70h] [rbp-90h] BYREF

  PropertyType = 0;
  RequiredSize = 0;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  ClassDevs = SetupDiGetClassDevsExW(0, 0, 0, 4u, 0, 0, 0);
  v3 = ClassDevs;
  if ( ClassDevs == (HDEVINFO)-1LL )
    return GetLastError();
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  DeviceInfoData.cbSize = 32;
  v4 = 0;
  v5 = 1;
  v6 = SetupDiEnumDeviceInfo(ClassDevs, 0, &DeviceInfoData);
LABEL_11:
  if ( v6 )
  {
    v7 = 0;
    while ( 1 )
    {
      memset_0(PropertyBuffer, 0, sizeof(PropertyBuffer));
      v8 = &DEVPKEY_Device_HardwareIds;
      if ( v7 )
        v8 = &DEVPKEY_Device_CompatibleIds;
      if ( SetupDiGetDevicePropertyW(v3, &DeviceInfoData, v8, &PropertyType, PropertyBuffer, 0x800u, &RequiredSize, 0) )
      {
        if ( PropertyType == 8210 )
        {
          if ( RequiredSize == 2 && !*(_WORD *)PropertyBuffer
            || RequiredSize >= 4 && (v12 = (unsigned __int64)RequiredSize >> 1, !v18[v12 + 1]) && !v18[v12] )
          {
            for ( i = PropertyBuffer; *(_WORD *)i; i += 2 * v14 + 2 )
            {
              pSetupStringTableAddString(*(_QWORD *)(a1 + 128), i, 0);
              v14 = -1;
              do
                ++v14;
              while ( *(_WORD *)&i[2 * v14] );
            }
          }
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LastError != 1168 )
        {
          v4 = LastError;
LABEL_10:
          v6 = SetupDiEnumDeviceInfo(v3, v5++, &DeviceInfoData);
          goto LABEL_11;
        }
      }
      if ( (unsigned int)++v7 >= 2 )
        goto LABEL_10;
    }
  }
  v10 = GetLastError();
  if ( v10 != 259 )
    v4 = v10;
  SetupDiDestroyDeviceInfoList(v3);
  return v4;
}

```

## disassembly

```asm
0x180006644  push    rbp
0x180006646  push    rbx
0x180006647  push    rsi
0x180006648  push    rdi
0x180006649  push    r12
0x18000664b  push    r13
0x18000664d  push    r14
0x18000664f  push    r15
0x180006651  lea     rbp, [rsp-788h]
0x180006659  sub     rsp, 888h
0x180006660  mov     rax, cs:__security_cookie
0x180006667  xor     rax, rsp
0x18000666a  mov     [rbp+7C0h+var_50], rax
0x180006671  xor     r12d, r12d
0x180006674  xorps   xmm0, xmm0
0x180006677  mov     r13, rcx
0x18000667a  mov     [rsp+8C0h+Reserved], r12; Reserved
0x18000667f  mov     [rsp+8C0h+MachineName], r12; MachineName
0x180006684  xor     r8d, r8d; hwndParent
0x180006687  xor     edx, edx; Enumerator
0x180006689  mov     [rsp+8C0h+PropertyType], r12d
0x18000668e  lea     r9d, [r12+4]; Flags
0x180006693  mov     [rsp+8C0h+RequiredSize], r12d
0x180006698  xor     ecx, ecx; ClassGuid
0x18000669a  mov     [rsp+8C0h+DeviceInfoSet], r12; DeviceInfoSet
0x18000669f  movups  xmmword ptr [rsp+8C0h+DeviceInfoData.cbSize], xmm0
0x1800066a4  movups  xmmword ptr [rsp+8C0h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x1800066a9  call    cs:__imp_SetupDiGetClassDevsExW
0x1800066af  mov     rsi, rax
0x1800066b2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800066b6  jnz     short loc_1800066C5
0x1800066b8  call    cs:__imp_GetLastError
0x1800066be  mov     ebx, eax
0x1800066c0  jmp     loc_1800067A0
0x1800066c5  xorps   xmm0, xmm0
0x1800066c8  lea     r8, [rsp+8C0h+DeviceInfoData]; DeviceInfoData
0x1800066cd  movups  xmmword ptr [rsp+8C0h+DeviceInfoData.cbSize], xmm0
0x1800066d2  xor     edx, edx; MemberIndex
0x1800066d4  mov     [rsp+8C0h+DeviceInfoData.cbSize], 20h ; ' '
0x1800066dc  mov     rcx, rsi; DeviceInfoSet
0x1800066df  mov     ebx, r12d
0x1800066e2  movups  xmmword ptr [rsp+8C0h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x1800066e7  mov     r15d, 1
0x1800066ed  call    cs:__imp_SetupDiEnumDeviceInfo
0x1800066f3  jmp     loc_180006781
0x1800066f8  mov     r14d, r12d
0x1800066fb  xor     edx, edx; Val
0x1800066fd  lea     rcx, [rsp+8C0h+PropertyBuffer]; void *
0x180006702  mov     r8d, 800h; Size
0x180006708  call    memset_0
0x18000670d  mov     [rsp+8C0h+Flags], r12d; Flags
0x180006712  lea     rax, DEVPKEY_Device_CompatibleIds
0x180006719  test    r14d, r14d
0x18000671c  lea     r8, DEVPKEY_Device_HardwareIds
0x180006723  lea     r9, [rsp+8C0h+PropertyType]; PropertyType
0x180006728  mov     rcx, rsi; DeviceInfoSet
0x18000672b  cmovnz  r8, rax; PropertyKey
0x18000672f  lea     rdx, [rsp+8C0h+DeviceInfoData]; DeviceInfoData
0x180006734  lea     rax, [rsp+8C0h+RequiredSize]
0x180006739  mov     [rsp+8C0h+Reserved], rax; RequiredSize
0x18000673e  lea     rax, [rsp+8C0h+PropertyBuffer]
0x180006743  mov     dword ptr [rsp+8C0h+MachineName], 800h; PropertyBufferSize
0x18000674b  mov     [rsp+8C0h+DeviceInfoSet], rax; PropertyBuffer
0x180006750  call    cs:__imp_SetupDiGetDevicePropertyW
0x180006756  test    eax, eax
0x180006758  jnz     short loc_1800067C5
0x18000675a  call    cs:__imp_GetLastError
0x180006760  cmp     eax, 490h
0x180006765  jz      loc_180006833
0x18000676b  mov     ebx, eax
0x18000676d  lea     r8, [rsp+8C0h+DeviceInfoData]; DeviceInfoData
0x180006772  mov     edx, r15d; MemberIndex
0x180006775  mov     rcx, rsi; DeviceInfoSet
0x180006778  call    cs:__imp_SetupDiEnumDeviceInfo
0x18000677e  inc     r15d
0x180006781  test    eax, eax
0x180006783  jnz     loc_1800066F8
0x180006789  call    cs:__imp_GetLastError
0x18000678f  cmp     eax, 103h
0x180006794  cmovnz  ebx, eax
0x180006797  mov     rcx, rsi; DeviceInfoSet
0x18000679a  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x1800067a0  mov     eax, ebx
0x1800067a2  mov     rcx, [rbp+7C0h+var_50]
0x1800067a9  xor     rcx, rsp; StackCookie
0x1800067ac  call    __security_check_cookie
0x1800067b1  add     rsp, 888h
0x1800067b8  pop     r15
0x1800067ba  pop     r14
0x1800067bc  pop     r13
0x1800067be  pop     r12
0x1800067c0  pop     rdi
0x1800067c1  pop     rsi
0x1800067c2  pop     rbx
0x1800067c3  pop     rbp
0x1800067c4  retn
0x1800067c5  cmp     [rsp+8C0h+PropertyType], 2012h
0x1800067cd  jnz     short loc_180006833
0x1800067cf  mov     eax, [rsp+8C0h+RequiredSize]
0x1800067d3  movzx   ecx, word ptr [rsp+8C0h+PropertyBuffer]
0x1800067d8  cmp     eax, 2
0x1800067db  jnz     short loc_1800067E2
0x1800067dd  test    cx, cx
0x1800067e0  jz      short loc_1800067FA
0x1800067e2  cmp     eax, 4
0x1800067e5  jb      short loc_180006833
0x1800067e7  shr     rax, 1
0x1800067ea  cmp     [rsp+rax*2+8C0h+var_852], r12w
0x1800067f0  jnz     short loc_180006833
0x1800067f2  cmp     [rsp+rax*2+8C0h+var_854], r12w
0x1800067f8  jnz     short loc_180006833
0x1800067fa  lea     rdi, [rsp+8C0h+PropertyBuffer]
0x1800067ff  test    cx, cx
0x180006802  jz      short loc_180006833
0x180006804  mov     rcx, [r13+80h]
0x18000680b  xor     r8d, r8d
0x18000680e  mov     rdx, rdi
0x180006811  call    cs:__imp_pSetupStringTableAddString
0x180006817  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000681b  inc     rax
0x18000681e  cmp     [rdi+rax*2], r12w
0x180006823  jnz     short loc_18000681B
0x180006825  lea     rdi, [rdi+rax*2]
0x180006829  add     rdi, 2
0x18000682d  cmp     [rdi], r12w
0x180006831  jnz     short loc_180006804
0x180006833  inc     r14d
0x180006836  cmp     r14d, 2
0x18000683a  jb      loc_1800066FB
0x180006840  jmp     loc_18000676D
```
