# PiDevCfgConfigureDeviceKeys

- ea: `0x1409afe48`
- end: `0x1409b0026`
- name: `PiDevCfgConfigureDeviceKeys`
- size: `478`
- prototype: ``
- caller_count: `6`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14076c398`
- `0x1409b055c`
- `0x1409b331c`
- `0x1409b4478`
- `0x140a7fc50`
- `0x140acd5d8`

## callees

- `0x1404ccbc4`
- `0x1405de948`
- `0x1406daa70`
- `0x1406daad0`
- `0x1409af29c`
- `0x1409afb54`
- `0x1409afe48`
- `0x1409b002c`
- `0x1409b00bc`
- `0x1409b45d4`
- `0x140acac3c`
- `0x140bae8e0`

## string_xrefs

- `0x140b624dc`: `ConfigFlags`
- `0x140b62497`: `ClassConfigured`

## pseudocode

```c
__int64 __fastcall PiDevCfgConfigureDeviceKeys(__int64 a1, __int64 a2, void *a3, int a4, _DWORD *a5, _DWORD *a6)
{
  int v9; // r12d
  int inited; // edi
  unsigned int *v12; // rcx
  unsigned int *v13; // rcx
  unsigned int *v14; // rcx
  __int64 v15; // [rsp+40h] [rbp-69h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-61h] BYREF
  __int128 v17; // [rsp+50h] [rbp-59h] BYREF
  _OWORD v18[2]; // [rsp+60h] [rbp-49h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-29h] BYREF

  KeyHandle = 0;
  v15 = 0;
  v9 = a1;
  v17 = 0;
  memset(v18, 0, sizeof(v18));
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  inited = PiDevCfgInitResolveContext(a1, a3, v18);
  if ( inited >= 0 )
  {
    inited = PiDevCfgEnumDeviceKeys(
               v9,
               a2,
               (_DWORD)a3,
               a4,
               1,
               (__int64)PiDevCfgConfigureDeviceKeyCallback,
               (__int64)v18);
    if ( inited >= 0 )
    {
      if ( (a4 & 8) == 0 || (inited = PiDevCfgConfigureDeviceInterfaces(*(_QWORD *)(a2 + 8), a3, v18), inited >= 0) )
      {
        if ( (a4 & 0x10) == 0 || (inited = PiDevCfgConfigureSoftwareDevices(*(_QWORD *)(a2 + 16), a3), inited >= 0) )
        {
          if ( (a4 & 0x200) == 0 || (inited = PiDevCfgConfigureDeviceFilters(*(_QWORD *)(a2 + 16), a3), inited >= 0) )
          {
            LODWORD(v17) = 917516;
            *((_QWORD *)&v17 + 1) = L"Status";
            *(_QWORD *)&ObjectAttributes.Length = 48;
            ObjectAttributes.ObjectName = (PUNICODE_STRING)&v17;
            *(_QWORD *)&ObjectAttributes.Attributes = 576;
            KeyHandle = 0;
            ObjectAttributes.RootDirectory = a3;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
            {
              if ( a6 )
              {
                if ( (int)PiDevCfgQueryResolveValue(v18, KeyHandle, L"Reboot", &v15) >= 0 )
                {
                  if ( (unsigned __int8)PnpValidateRegistryDword(v15) && *(unsigned int *)((char *)v12 + v12[2]) )
                    *a6 |= 0x40u;
                  ExFreePoolWithTag(v12, 0);
                }
                if ( (int)PiDevCfgQueryResolveValue(v18, KeyHandle, L"ClassConfigured", &v15) >= 0 )
                {
                  if ( (unsigned __int8)PnpValidateRegistryDword(v15) && *(unsigned int *)((char *)v13 + v13[2]) )
                    *a6 |= 2u;
                  ExFreePoolWithTag(v13, 0);
                }
              }
              if ( a5 && (int)PiDevCfgQueryResolveValue(v18, KeyHandle, L"ConfigFlags", &v15) >= 0 )
              {
                if ( (unsigned __int8)PnpValidateRegistryDword(v15) )
                  *a5 |= *(unsigned int *)((char *)v14 + v14[2]);
                ExFreePoolWithTag(v14, 0);
              }
            }
          }
        }
      }
    }
  }
  PiDevCfgFreeResolveContext(v18);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1409afe48  push    rbp
0x1409afe4a  push    rbx
0x1409afe4b  push    rsi
0x1409afe4c  push    rdi
0x1409afe4d  push    r12
0x1409afe4f  push    r13
0x1409afe51  push    r14
0x1409afe53  push    r15
0x1409afe55  lea     rbp, [rsp-0Fh]
0x1409afe5a  sub     rsp, 0B8h
0x1409afe61  mov     rsi, [rbp+47h+arg_20]
0x1409afe65  xor     eax, eax
0x1409afe67  mov     [rbp+47h+KeyHandle], rax
0x1409afe6b  xorps   xmm1, xmm1
0x1409afe6e  mov     [rbp+47h+var_B0], rax
0x1409afe72  xorps   xmm0, xmm0
0x1409afe75  mov     r15d, r9d
0x1409afe78  mov     r14, r8
0x1409afe7b  mov     r13, rdx
0x1409afe7e  mov     r12, rcx
0x1409afe81  movups  [rbp+47h+var_A0], xmm0
0x1409afe85  movups  [rbp+47h+var_90], xmm1
0x1409afe89  movups  [rbp+47h+var_80], xmm1
0x1409afe8d  test    rsi, rsi
0x1409afe90  jz      short loc_1409AFE94
0x1409afe92  mov     [rsi], eax
0x1409afe94  mov     rbx, [rbp+47h+arg_28]
0x1409afe98  test    rbx, rbx
0x1409afe9b  jz      short loc_1409AFE9F
0x1409afe9d  mov     [rbx], eax
0x1409afe9f  lea     r8, [rbp+47h+var_90]
0x1409afea3  mov     rdx, r14
0x1409afea6  call    PiDevCfgInitResolveContext
0x1409afeab  mov     edi, eax
0x1409afead  test    eax, eax
0x1409afeaf  js      short loc_1409AFEE5
0x1409afeb1  lea     rax, [rbp+47h+var_90]
0x1409afeb5  mov     r9d, r15d
0x1409afeb8  mov     [rsp+0F0h+var_C0], rax
0x1409afebd  mov     r8, r14
0x1409afec0  lea     rax, PiDevCfgConfigureDeviceKeyCallback
0x1409afec7  mov     rdx, r13
0x1409afeca  mov     [rsp+0F0h+var_C8], rax
0x1409afecf  mov     rcx, r12
0x1409afed2  mov     [rsp+0F0h+var_D0], 1
0x1409afed7  call    PiDevCfgEnumDeviceKeys
0x1409afedc  xor     r12d, r12d
0x1409afedf  mov     edi, eax
0x1409afee1  test    eax, eax
0x1409afee3  jns     short loc_1409AFF12
0x1409afee5  lea     rcx, [rbp+47h+var_90]
0x1409afee9  call    PiDevCfgFreeResolveContext
0x1409afeee  mov     rcx, [rbp+47h+KeyHandle]; Handle
0x1409afef2  test    rcx, rcx
0x1409afef5  jnz     loc_1409B001C
0x1409afefb  mov     eax, edi
0x1409afefd  add     rsp, 0B8h
0x1409aff04  pop     r15
0x1409aff06  pop     r14
0x1409aff08  pop     r13
0x1409aff0a  pop     r12
0x1409aff0c  pop     rdi
0x1409aff0d  pop     rsi
0x1409aff0e  pop     rbx
0x1409aff0f  pop     rbp
0x1409aff10  retn
0x1409aff12  test    r15b, 8
0x1409aff16  jnz     loc_1409AFFE2
0x1409aff1c  test    r15b, 10h
0x1409aff20  jz      short loc_1409AFF34
0x1409aff22  mov     rcx, [r13+10h]
0x1409aff26  mov     rdx, r14
0x1409aff29  call    PiDevCfgConfigureSoftwareDevices
0x1409aff2e  mov     edi, eax
0x1409aff30  test    eax, eax
0x1409aff32  js      short loc_1409AFEE5
0x1409aff34  bt      r15d, 9
0x1409aff39  jb      loc_1409B0001
0x1409aff3f  lea     rax, aStatus; "Status"
0x1409aff46  mov     dword ptr [rbp+47h+var_A0], 0E000Ch
0x1409aff4d  mov     qword ptr [rbp+47h+var_A0+8], rax
0x1409aff51  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x1409aff55  lea     rax, [rbp+47h+var_A0]
0x1409aff59  mov     qword ptr [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x1409aff61  xorps   xmm0, xmm0
0x1409aff64  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x1409aff68  mov     edx, 20019h; DesiredAccess
0x1409aff6d  mov     qword ptr [rbp+47h+ObjectAttributes.Attributes], 240h
0x1409aff75  lea     rcx, [rbp+47h+KeyHandle]; KeyHandle
0x1409aff79  mov     [rbp+47h+KeyHandle], r12
0x1409aff7d  mov     [rbp+47h+ObjectAttributes.RootDirectory], r14
0x1409aff81  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x1409aff86  call    ZwOpenKey
0x1409aff8b  test    eax, eax
0x1409aff8d  js      loc_1409AFEE5
0x1409aff93  test    rbx, rbx
0x1409aff96  jz      loc_140B624CB
0x1409aff9c  mov     rdx, [rbp+47h+KeyHandle]
0x1409affa0  lea     r9, [rbp+47h+var_B0]
0x1409affa4  lea     r8, aReboot; "Reboot"
0x1409affab  lea     rcx, [rbp+47h+var_90]
0x1409affaf  call    PiDevCfgQueryResolveValue
0x1409affb4  test    eax, eax
0x1409affb6  js      loc_140B6248F
0x1409affbc  mov     rcx, [rbp+47h+var_B0]
0x1409affc0  call    PnpValidateRegistryDword
0x1409affc5  test    al, al
0x1409affc7  jz      loc_140B62488
0x1409affcd  mov     eax, [rcx+8]
0x1409affd0  cmp     [rax+rcx], r12d
0x1409affd4  jz      loc_140B62488
0x1409affda  or      dword ptr [rbx], 40h
0x1409affdd  jmp     loc_140B62488
0x1409affe2  mov     rcx, [r13+8]
0x1409affe6  lea     r8, [rbp+47h+var_90]
0x1409affea  mov     rdx, r14
0x1409affed  call    PiDevCfgConfigureDeviceInterfaces
0x1409afff2  mov     edi, eax
0x1409afff4  test    eax, eax
0x1409afff6  jns     loc_1409AFF1C
0x1409afffc  jmp     loc_1409AFEE5
0x1409b0001  mov     rcx, [r13+10h]
0x1409b0005  mov     rdx, r14
0x1409b0008  call    PiDevCfgConfigureDeviceFilters
0x1409b000d  mov     edi, eax
0x1409b000f  test    eax, eax
0x1409b0011  js      loc_1409AFEE5
0x1409b0017  jmp     loc_1409AFF3F
0x1409b001c  call    ZwClose
0x1409b0021  jmp     loc_1409AFEFB
0x140b62488  xor     edx, edx; Tag
0x140b6248a  call    ExFreePoolWithTag
0x140b6248f  mov     rdx, [rbp+47h+KeyHandle]
0x140b62493  lea     r9, [rbp+47h+var_B0]
0x140b62497  lea     r8, aClassconfigure; "ClassConfigured"
0x140b6249e  lea     rcx, [rbp+47h+var_90]
0x140b624a2  call    PiDevCfgQueryResolveValue
0x140b624a7  test    eax, eax
0x140b624a9  js      short loc_140B624CB
0x140b624ab  mov     rcx, [rbp+47h+var_B0]
0x140b624af  call    PnpValidateRegistryDword
0x140b624b4  test    al, al
0x140b624b6  jz      short loc_140B624C4
0x140b624b8  mov     eax, [rcx+8]
0x140b624bb  cmp     [rax+rcx], r12d
0x140b624bf  jz      short loc_140B624C4
0x140b624c1  or      dword ptr [rbx], 2
0x140b624c4  xor     edx, edx; Tag
0x140b624c6  call    ExFreePoolWithTag
0x140b624cb  test    rsi, rsi
0x140b624ce  jz      loc_1409AFEE5
0x140b624d4  mov     rdx, [rbp+47h+KeyHandle]
0x140b624d8  lea     r9, [rbp+47h+var_B0]
0x140b624dc  lea     r8, aConfigflags; "ConfigFlags"
0x140b624e3  lea     rcx, [rbp+47h+var_90]
0x140b624e7  call    PiDevCfgQueryResolveValue
0x140b624ec  test    eax, eax
0x140b624ee  js      loc_1409AFEE5
0x140b624f4  mov     rcx, [rbp+47h+var_B0]
0x140b624f8  call    PnpValidateRegistryDword
0x140b624fd  test    al, al
0x140b624ff  jz      short loc_140B62509
0x140b62501  mov     eax, [rcx+8]
0x140b62504  mov     edx, [rax+rcx]
0x140b62507  or      [rsi], edx
0x140b62509  xor     edx, edx; Tag
0x140b6250b  call    ExFreePoolWithTag
0x140b62510  nop
0x140b62511  jmp     loc_1409AFEE5
```
