# PopulateValidDeviceDirectories

- ea: `0x180007fbc`
- end: `0x180008296`
- name: `PopulateValidDeviceDirectories`
- size: `730`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18000829c`

## callees

- `0x180007f48`
- `0x180007fbc`
- `0x180008e30`
- `0x18000a010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800081b8`
- `msvcrt!wcschr` at `0x1800081b8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180008172`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180008172`
- `KERNEL32!GetLastError` at `0x180008045`
- `KERNEL32!GetLastError` at `0x1800080fa`
- `KERNEL32!GetLastError` at `0x180008276`
- `KERNEL32!GetLastError` at `0x180008281`
- `KERNEL32!GetLastError` at `0x180008045`
- `KERNEL32!GetLastError` at `0x1800080fa`
- `KERNEL32!GetLastError` at `0x180008276`
- `KERNEL32!GetLastError` at `0x180008281`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000823d`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000823d`
- `SETUPAPI!pSetupStringTableAddString` at `0x1800081f6`
- `SETUPAPI!pSetupStringTableAddString` at `0x1800081f6`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800080ec`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800080ec`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x180008036`
- `SETUPAPI!SetupDiGetClassDevsExW` at `0x180008036`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000807a`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000807a`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800080a2`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800080a2`

## pseudocode

```c
__int64 __fastcall PopulateValidDeviceDirectories(__int64 a1, __int64 a2, _DWORD *a3)
{
  _DWORD *v3; // rbx
  __int64 v4; // rdi
  HDEVINFO ClassDevs; // r15
  DWORD v7; // ebx
  DWORD v8; // r12d
  __int64 v9; // rax
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  BYTE *v12; // r8
  BYTE *v13; // rcx
  __int64 v14; // rdi
  int v15; // esi
  wchar_t v16; // dx
  DWORD LastError; // eax
  HDEVINFO DeviceInfoSet; // [rsp+20h] [rbp-E0h]
  DWORD RequiredSize; // [rsp+40h] [rbp-C0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h]
  _DWORD *v23; // [rsp+50h] [rbp-B0h]
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+58h] [rbp-A8h] BYREF
  BYTE PropertyBuffer[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR DeviceInstanceId[200]; // [rsp+290h] [rbp+190h] BYREF

  v22 = a2;
  v3 = a3;
  *a3 = 0;
  v4 = a2;
  v23 = a3;
  PropertyType = 0;
  RequiredSize = 0;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  ClassDevs = SetupDiGetClassDevsExW(0, 0, 0, 4u, 0, 0, 0);
  if ( ClassDevs == (HDEVINFO)-1LL )
  {
    return GetLastError();
  }
  else
  {
    v8 = 0;
    memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
    DeviceInfoData.cbSize = 32;
    while ( 1 )
    {
      if ( !(unsigned int)PnpCleanFilesNotifyCallback(a1) )
      {
        v7 = 1223;
LABEL_33:
        LODWORD(DeviceInfoSet) = v7;
        (*(void (**)(_QWORD, __int64, _QWORD, const char *, ...))(a1 + 40))(
          *(_QWORD *)(a1 + 48),
          1,
          0,
          "Failed to populate list of valid device directories, Err = 0x%lx",
          DeviceInfoSet);
        goto LABEL_34;
      }
      if ( !SetupDiEnumDeviceInfo(ClassDevs, v8, &DeviceInfoData) )
        break;
      if ( !SetupDiGetDeviceInstanceIdW(ClassDevs, &DeviceInfoData, DeviceInstanceId, 0xC8u, 0) )
      {
        LastError = GetLastError();
        goto LABEL_39;
      }
      DeviceInstanceId[199] = 0;
      if ( !SetupDiGetDevicePropertyW(
              ClassDevs,
              &DeviceInfoData,
              &DEVPKEY_Device_StateDirectoryId,
              &PropertyType,
              PropertyBuffer,
              0x208u,
              &RequiredSize,
              0) )
      {
        v7 = GetLastError();
        if ( v7 == 1168 )
        {
          v9 = 2147483646;
          v10 = DeviceInstanceId;
          v11 = 260;
          v12 = PropertyBuffer;
          do
          {
            if ( !v9 )
              break;
            if ( !*v10 )
              break;
            *(_WORD *)v12 = *v10++;
            v12 += 2;
            --v9;
            --v11;
          }
          while ( v11 );
          v13 = v12 - 2;
          if ( v11 )
            v13 = v12;
          *(_WORD *)v13 = 0;
          if ( v11 )
          {
            v7 = 0;
            v14 = -1;
            do
              ++v14;
            while ( *(_WORD *)&PropertyBuffer[2 * v14] );
            v15 = 0;
            if ( (_DWORD)v14 )
            {
              while ( 1 )
              {
                v16 = *(_WORD *)&PropertyBuffer[2 * v15];
                if ( v16 > 0x7Fu )
                  break;
                if ( v16 < 0x20u || wcschr(L"\"*+,/:;<=>?[\\]|", v16) )
                  *(_WORD *)&PropertyBuffer[2 * v15] = 35;
                if ( ++v15 >= (unsigned int)v14 )
                  goto LABEL_26;
              }
              v7 = 87;
            }
LABEL_26:
            v4 = v22;
          }
          else
          {
            *(_WORD *)PropertyBuffer = 0;
            v7 = RtlNtStatusToDosErrorNoTeb(-2147483643);
          }
        }
        if ( v7 )
          goto LABEL_33;
        v3 = v23;
      }
      if ( (unsigned int)pSetupStringTableAddString(v4, PropertyBuffer, 0) == -1 )
      {
        v7 = 8;
        goto LABEL_33;
      }
      ++v8;
      ++*v3;
    }
    v7 = 0;
    LastError = GetLastError();
    if ( LastError == 259 )
      goto LABEL_34;
LABEL_39:
    v7 = LastError;
    if ( LastError )
      goto LABEL_33;
LABEL_34:
    SetupDiDestroyDeviceInfoList(ClassDevs);
  }
  return v7;
}

```

## disassembly

```asm
0x180007fbc  mov     [rsp-8+arg_18], rbx
0x180007fc1  push    rbp
0x180007fc2  push    rsi
0x180007fc3  push    rdi
0x180007fc4  push    r12
0x180007fc6  push    r13
0x180007fc8  push    r14
0x180007fca  push    r15
0x180007fcc  lea     rbp, [rsp-330h]
0x180007fd4  sub     rsp, 430h
0x180007fdb  mov     rax, cs:__security_cookie
0x180007fe2  xor     rax, rsp
0x180007fe5  mov     [rbp+360h+var_40], rax
0x180007fec  xor     r14d, r14d
0x180007fef  mov     [rsp+460h+var_418], rdx
0x180007ff4  mov     rbx, r8
0x180007ff7  mov     [r8], r14d
0x180007ffa  xorps   xmm0, xmm0
0x180007ffd  mov     [rsp+460h+Reserved], r14; Reserved
0x180008002  mov     rdi, rdx
0x180008005  mov     [rsp+460h+MachineName], r14; MachineName
0x18000800a  mov     r13, rcx
0x18000800d  mov     [rsp+460h+var_410], rbx
0x180008012  lea     r9d, [r14+4]; Flags
0x180008016  mov     [rsp+460h+PropertyType], r14d
0x18000801b  xor     r8d, r8d; hwndParent
0x18000801e  mov     [rsp+460h+RequiredSize], r14d
0x180008023  xor     edx, edx; Enumerator
0x180008025  mov     [rsp+460h+DeviceInfoSet], r14; DeviceInfoSet
0x18000802a  xor     ecx, ecx; ClassGuid
0x18000802c  movups  xmmword ptr [rsp+460h+DeviceInfoData.cbSize], xmm0
0x180008031  movups  xmmword ptr [rsp+460h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x180008036  call    cs:__imp_SetupDiGetClassDevsExW
0x18000803c  mov     r15, rax
0x18000803f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008043  jnz     short loc_180008052
0x180008045  call    cs:__imp_GetLastError
0x18000804b  mov     ebx, eax
0x18000804d  jmp     loc_180008243
0x180008052  xorps   xmm0, xmm0
0x180008055  mov     r12d, r14d
0x180008058  movups  xmmword ptr [rsp+460h+DeviceInfoData.cbSize], xmm0
0x18000805d  mov     [rsp+460h+DeviceInfoData.cbSize], 20h ; ' '
0x180008065  movups  xmmword ptr [rsp+460h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x18000806a  jmp     loc_180008206
0x18000806f  lea     r8, [rsp+460h+DeviceInfoData]; DeviceInfoData
0x180008074  mov     edx, r12d; MemberIndex
0x180008077  mov     rcx, r15; DeviceInfoSet
0x18000807a  call    cs:__imp_SetupDiEnumDeviceInfo
0x180008080  test    eax, eax
0x180008082  jz      loc_18000827E
0x180008088  mov     r9d, 0C8h; DeviceInstanceIdSize
0x18000808e  mov     [rsp+460h+DeviceInfoSet], r14; RequiredSize
0x180008093  lea     r8, [rbp+360h+DeviceInstanceId]; DeviceInstanceId
0x18000809a  mov     rcx, r15; DeviceInfoSet
0x18000809d  lea     rdx, [rsp+460h+DeviceInfoData]; DeviceInfoData
0x1800080a2  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x1800080a8  test    eax, eax
0x1800080aa  jz      loc_180008276
0x1800080b0  mov     [rsp+460h+Flags], r14d; Flags
0x1800080b5  lea     rax, [rsp+460h+RequiredSize]
0x1800080ba  mov     [rsp+460h+Reserved], rax; RequiredSize
0x1800080bf  lea     r9, [rsp+460h+PropertyType]; PropertyType
0x1800080c4  lea     rax, [rbp+360h+PropertyBuffer]
0x1800080c8  mov     dword ptr [rsp+460h+MachineName], 208h; PropertyBufferSize
0x1800080d0  lea     r8, DEVPKEY_Device_StateDirectoryId; PropertyKey
0x1800080d7  mov     [rsp+460h+DeviceInfoSet], rax; PropertyBuffer
0x1800080dc  lea     rdx, [rsp+460h+DeviceInfoData]; DeviceInfoData
0x1800080e1  mov     [rbp+360h+var_42], r14w
0x1800080e9  mov     rcx, r15; DeviceInfoSet
0x1800080ec  call    cs:__imp_SetupDiGetDevicePropertyW
0x1800080f2  test    eax, eax
0x1800080f4  jnz     loc_1800081EC
0x1800080fa  call    cs:__imp_GetLastError
0x180008100  mov     ebx, eax
0x180008102  cmp     eax, 490h
0x180008107  jnz     loc_1800081E3
0x18000810d  mov     eax, 7FFFFFFEh
0x180008112  lea     rcx, [rbp+360h+DeviceInstanceId]
0x180008119  mov     edx, 104h
0x18000811e  lea     r8, [rbp+360h+PropertyBuffer]
0x180008122  test    rax, rax
0x180008125  jz      short loc_180008146
0x180008127  movzx   r9d, word ptr [rcx]
0x18000812b  test    r9w, r9w
0x18000812f  jz      short loc_180008146
0x180008131  mov     [r8], r9w
0x180008135  add     rcx, 2
0x180008139  add     r8, 2
0x18000813d  dec     rax
0x180008140  sub     rdx, 1
0x180008144  jnz     short loc_180008122
0x180008146  mov     rax, rdx
0x180008149  lea     rcx, [r8-2]
0x18000814d  neg     rax
0x180008150  sbb     r9d, r9d
0x180008153  not     r9d
0x180008156  and     r9d, 80000005h
0x18000815d  test    rdx, rdx
0x180008160  cmovnz  rcx, r8
0x180008164  mov     [rcx], r14w
0x180008168  jnz     short loc_18000817C
0x18000816a  mov     ecx, r9d; Status
0x18000816d  mov     word ptr [rbp+360h+PropertyBuffer], r14w
0x180008172  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180008178  mov     ebx, eax
0x18000817a  jmp     short loc_1800081E3
0x18000817c  mov     ebx, r14d
0x18000817f  lea     rax, [rbp+360h+PropertyBuffer]
0x180008183  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180008187  inc     rdi
0x18000818a  cmp     [rax+rdi*2], r14w
0x18000818f  jnz     short loc_180008187
0x180008191  mov     esi, r14d
0x180008194  test    edi, edi
0x180008196  jz      short loc_1800081DE
0x180008198  mov     r14d, esi
0x18000819b  movzx   edx, word ptr [rbp+r14*2+360h+PropertyBuffer]; Ch
0x1800081a1  cmp     dx, 7Fh
0x1800081a5  ja      short loc_1800081D6
0x1800081a7  mov     eax, 20h ; ' '
0x1800081ac  cmp     dx, ax
0x1800081af  jb      short loc_1800081C3
0x1800081b1  lea     rcx, Str; "\"*+,/:;<=>?[\\]|"
0x1800081b8  call    cs:__imp_wcschr
0x1800081be  test    rax, rax
0x1800081c1  jz      short loc_1800081CE
0x1800081c3  mov     eax, 23h ; '#'
0x1800081c8  mov     word ptr [rbp+r14*2+360h+PropertyBuffer], ax
0x1800081ce  inc     esi
0x1800081d0  cmp     esi, edi
0x1800081d2  jb      short loc_180008198
0x1800081d4  jmp     short loc_1800081DB
0x1800081d6  mov     ebx, 57h ; 'W'
0x1800081db  xor     r14d, r14d
0x1800081de  mov     rdi, [rsp+460h+var_418]
0x1800081e3  test    ebx, ebx
0x1800081e5  jnz     short loc_18000821B
0x1800081e7  mov     rbx, [rsp+460h+var_410]
0x1800081ec  xor     r8d, r8d
0x1800081ef  lea     rdx, [rbp+360h+PropertyBuffer]
0x1800081f3  mov     rcx, rdi
0x1800081f6  call    cs:__imp_pSetupStringTableAddString
0x1800081fc  cmp     eax, 0FFFFFFFFh
0x1800081ff  jz      short loc_18000826F
0x180008201  inc     r12d
0x180008204  inc     dword ptr [rbx]
0x180008206  mov     rcx, r13
0x180008209  call    PnpCleanFilesNotifyCallback
0x18000820e  test    eax, eax
0x180008210  jnz     loc_18000806F
0x180008216  mov     ebx, 4C7h
0x18000821b  mov     rcx, [r13+30h]
0x18000821f  lea     r9, aFailedToPopula; "Failed to populate list of valid device"...
0x180008226  mov     rax, [r13+28h]
0x18000822a  xor     r8d, r8d
0x18000822d  mov     dword ptr [rsp+460h+DeviceInfoSet], ebx
0x180008231  lea     edx, [r8+1]
0x180008235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000823a  mov     rcx, r15; DeviceInfoSet
0x18000823d  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180008243  mov     eax, ebx
0x180008245  mov     rcx, [rbp+360h+var_40]
0x18000824c  xor     rcx, rsp; StackCookie
0x18000824f  call    __security_check_cookie
0x180008254  mov     rbx, [rsp+460h+arg_18]
0x18000825c  add     rsp, 430h
0x180008263  pop     r15
0x180008265  pop     r14
0x180008267  pop     r13
0x180008269  pop     r12
0x18000826b  pop     rdi
0x18000826c  pop     rsi
0x18000826d  pop     rbp
0x18000826e  retn
0x18000826f  mov     ebx, 8
0x180008274  jmp     short loc_18000821B
0x180008276  call    cs:__imp_GetLastError
0x18000827c  jmp     short loc_18000828E
0x18000827e  mov     ebx, r14d
0x180008281  call    cs:__imp_GetLastError
0x180008287  cmp     eax, 103h
0x18000828c  jz      short loc_18000823A
0x18000828e  mov     ebx, eax
0x180008290  test    eax, eax
0x180008292  jz      short loc_18000823A
0x180008294  jmp     short loc_18000821B
```
