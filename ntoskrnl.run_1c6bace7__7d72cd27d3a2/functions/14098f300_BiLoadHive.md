# BiLoadHive

- ea: `0x14098f300`
- end: `0x14098f5de`
- name: `BiLoadHive`
- size: `734`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1409928ac`

## callees

- `0x140403380`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406df5c0`
- `0x1406df5e0`
- `0x1406e0f20`
- `0x14098f300`
- `0x14098f5e4`
- `0x1409908b8`
- `0x140990954`
- `0x140992794`
- `0x140993780`

## string_xrefs

- `0x14098f397`: `\Registry\Machine`
- `0x14098f3b5`: `\Registry\Machine`
- `0x14098f477`: `\Registry\Machine`
- `0x14098f56f`: `Failed open newly loaded key %ws. Flags: 0x%x Status: %x`
- `0x14098f3bc`: `Failed open key %ws. Status: %x`

## pseudocode

```c
__int64 __fastcall BiLoadHive(PCWSTR SourceString, __int64 a2, HANDLE *a3)
{
  unsigned int i; // esi
  void *v6; // rdi
  NTSTATUS v7; // ebx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rcx
  __int64 v12; // [rsp+20h] [rbp-D8h]
  __int64 v13; // [rsp+28h] [rbp-D0h]
  __int64 v14; // [rsp+30h] [rbp-C8h] BYREF
  void *v15; // [rsp+38h] [rbp-C0h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-B8h] BYREF
  _BYTE v17[48]; // [rsp+70h] [rbp-88h] BYREF
  UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-58h] BYREF
  UNICODE_STRING v19; // [rsp+B0h] [rbp-48h] BYREF

  memset(v17, 0, 44);
  memset(&ObjectAttributes, 0, 44);
  v14 = 0;
  v19 = 0;
  DestinationString = 0;
  for ( i = 0; ; ++i )
  {
    v6 = 0;
    v15 = 0;
    if ( (unsigned __int8)BiDoesHiveExist(a2) )
    {
      v8 = BiOpenKeyNonBcd(0, L"\\Registry\\Machine", 983103, &v15);
      v7 = v8;
      if ( v8 >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, SourceString);
        ObjectAttributes.Length = 48;
        v6 = v15;
        ObjectAttributes.RootDirectory = v15;
        ObjectAttributes.Attributes = 576;
        ObjectAttributes.ObjectName = &DestinationString;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        RtlInitUnicodeString(&v19, (PCWSTR)(a2 + 12));
        *(_DWORD *)v17 = 48;
        *(_QWORD *)&v17[8] = 0;
        *(_DWORD *)&v17[24] = 576;
        *(_QWORD *)&v17[16] = &v19;
        *(_OWORD *)&v17[32] = 0;
        v9 = BiAcquirePrivilege(18, &v14);
        v7 = v9;
        if ( v9 >= 0 )
        {
          v7 = ZwLoadKey2(&ObjectAttributes, v17, 6016);
          if ( v7 < 0 )
            v7 = ZwLoadKey2(&ObjectAttributes, v17, 4992);
          if ( v7 < 0 )
            v7 = ZwLoadKey(&ObjectAttributes, v17);
          BiReleasePrivilege(&v14);
          if ( v7 >= 0 )
          {
            v7 = ZwOpenKey(a3, 0x20019u, &ObjectAttributes);
            if ( v7 < 0 )
            {
              BiAcquirePrivilege(17, &v14);
              ZwUnloadKey(&ObjectAttributes);
              BiReleasePrivilege(&v14);
              LODWORD(v12) = v7;
              BiLogMessage(4, L"Failed open newly loaded key %ws. Flags: 0x%x Status: %x", SourceString, 576, v12);
            }
          }
          else
          {
            v10 = 2;
            if ( v7 != -1073741790 )
              v10 = 4;
            LODWORD(v13) = v7;
            BiLogMessage(
              v10,
              L"Failed load key %ws. Flags: 0x%x File: %s Status: %x",
              SourceString,
              576,
              a2 + 12,
              v13,
              v14);
          }
        }
        else
        {
          BiLogMessage(
            4,
            L"Failed to acquire permissions to load hive. Status: %x",
            L"\\Registry\\Machine",
            (unsigned int)v9);
        }
      }
      else
      {
        BiLogMessage(4, L"Failed open key %ws. Status: %x", L"\\Registry\\Machine", (unsigned int)v8);
        v6 = v15;
      }
    }
    else
    {
      v7 = -1073741809;
    }
    if ( v6 )
      ZwClose(v6);
    if ( v7 != -1073741443 )
      break;
    __debugbreak();
    if ( i >= 5 )
      break;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14098f300  mov     r11, rsp
0x14098f303  mov     [r11+18h], r8
0x14098f307  mov     [r11+10h], rdx
0x14098f30b  mov     [r11+8], rcx
0x14098f30f  push    rbx
0x14098f310  push    rsi
0x14098f311  push    rdi
0x14098f312  push    r12
0x14098f314  push    r13
0x14098f316  push    r14
0x14098f318  push    r15
0x14098f31a  sub     rsp, 0C0h
0x14098f321  mov     r13, rdx
0x14098f324  mov     r15, rcx
0x14098f327  xor     eax, eax
0x14098f329  xorps   xmm0, xmm0
0x14098f32c  movups  [rsp+0F8h+var_88], xmm0
0x14098f331  movups  xmmword ptr [r11-78h], xmm0
0x14098f336  movups  xmmword ptr [r11-6Ch], xmm0
0x14098f33b  movups  xmmword ptr [rsp+0F8h+ObjectAttributes.Length], xmm0
0x14098f340  movups  xmmword ptr [rsp+0F8h+ObjectAttributes.ObjectName], xmm0
0x14098f345  movups  xmmword ptr [rsp+0F8h+ObjectAttributes+1Ch], xmm0
0x14098f34a  mov     [rsp+0F8h+var_C8], rax
0x14098f34f  movups  xmmword ptr [r11-48h], xmm0
0x14098f354  xorps   xmm1, xmm1
0x14098f357  movups  xmmword ptr [r11-58h], xmm1
0x14098f35c  xor     esi, esi
0x14098f35e  lea     r14d, [rax+4]
0x14098f362  mov     r12d, 240h
0x14098f368  xor     edi, edi
0x14098f36a  mov     [rsp+0F8h+var_C0], rdi
0x14098f36f  mov     rcx, r13
0x14098f372  call    BiDoesHiveExist
0x14098f377  test    al, al
0x14098f379  jnz     short loc_14098F38C
0x14098f37b  mov     ebx, 0C000000Fh
0x14098f380  mov     [rsp+0F8h+arg_18], ebx
0x14098f387  jmp     loc_14098F57E
0x14098f38c  lea     r9, [rsp+0F8h+var_C0]
0x14098f391  mov     r8d, 0F003Fh
0x14098f397  lea     rdx, aRegistryMachin_230; "\\Registry\\Machine"
0x14098f39e  xor     ecx, ecx
0x14098f3a0  call    BiOpenKeyNonBcd
0x14098f3a5  mov     ebx, eax
0x14098f3a7  mov     [rsp+0F8h+arg_18], eax
0x14098f3ae  test    eax, eax
0x14098f3b0  jns     short loc_14098F3D5
0x14098f3b2  mov     r9d, eax
0x14098f3b5  lea     r8, aRegistryMachin_230; "\\Registry\\Machine"
0x14098f3bc  lea     rdx, aFailedOpenKeyW; "Failed open key %ws. Status: %x"
0x14098f3c3  mov     ecx, r14d
0x14098f3c6  call    BiLogMessage
0x14098f3cb  mov     rdi, [rsp+0F8h+var_C0]
0x14098f3d0  jmp     loc_14098F57E
0x14098f3d5  mov     rdx, r15; SourceString
0x14098f3d8  lea     rcx, [rsp+0F8h+DestinationString]; DestinationString
0x14098f3e0  call    RtlInitUnicodeString
0x14098f3e5  mov     [rsp+0F8h+ObjectAttributes.Length], 30h ; '0'
0x14098f3ed  mov     rdi, [rsp+0F8h+var_C0]
0x14098f3f2  mov     [rsp+0F8h+ObjectAttributes.RootDirectory], rdi
0x14098f3f7  mov     [rsp+0F8h+ObjectAttributes.Attributes], r12d
0x14098f3fc  lea     rax, [rsp+0F8h+DestinationString]
0x14098f404  mov     [rsp+0F8h+ObjectAttributes.ObjectName], rax
0x14098f409  xorps   xmm0, xmm0
0x14098f40c  movdqu  xmmword ptr [rsp+0F8h+ObjectAttributes.SecurityDescriptor], xmm0
0x14098f412  lea     rdx, [r13+0Ch]; SourceString
0x14098f416  lea     rcx, [rsp+0F8h+var_48]; DestinationString
0x14098f41e  call    RtlInitUnicodeString
0x14098f423  mov     dword ptr [rsp+0F8h+var_88], 30h ; '0'
0x14098f42b  mov     qword ptr [rsp+0F8h+var_88+8], 0
0x14098f434  mov     [rsp+0F8h+var_70], r12d
0x14098f43c  lea     rax, [rsp+0F8h+var_48]
0x14098f444  mov     [rsp+0F8h+var_78], rax
0x14098f44c  xorps   xmm0, xmm0
0x14098f44f  movdqu  [rsp+0F8h+var_68], xmm0
0x14098f458  lea     rdx, [rsp+0F8h+var_C8]
0x14098f45d  mov     ecx, 12h
0x14098f462  call    BiAcquirePrivilege
0x14098f467  mov     ebx, eax
0x14098f469  mov     [rsp+0F8h+arg_18], eax
0x14098f470  test    eax, eax
0x14098f472  jns     short loc_14098F492
0x14098f474  mov     r9d, eax
0x14098f477  lea     r8, aRegistryMachin_230; "\\Registry\\Machine"
0x14098f47e  lea     rdx, aFailedToAcquir; "Failed to acquire permissions to load h"...
0x14098f485  mov     ecx, r14d
0x14098f488  call    BiLogMessage
0x14098f48d  jmp     loc_14098F57E
0x14098f492  mov     r8d, 1780h
0x14098f498  lea     rdx, [rsp+0F8h+var_88]
0x14098f49d  lea     rcx, [rsp+0F8h+ObjectAttributes]
0x14098f4a2  call    ZwLoadKey2
0x14098f4a7  mov     ebx, eax
0x14098f4a9  test    eax, eax
0x14098f4ab  jns     short loc_14098F4C4
0x14098f4ad  mov     r8d, 1380h
0x14098f4b3  lea     rdx, [rsp+0F8h+var_88]
0x14098f4b8  lea     rcx, [rsp+0F8h+ObjectAttributes]
0x14098f4bd  call    ZwLoadKey2
0x14098f4c2  mov     ebx, eax
0x14098f4c4  test    ebx, ebx
0x14098f4c6  jns     short loc_14098F4D9
0x14098f4c8  lea     rdx, [rsp+0F8h+var_88]
0x14098f4cd  lea     rcx, [rsp+0F8h+ObjectAttributes]
0x14098f4d2  call    ZwLoadKey
0x14098f4d7  mov     ebx, eax
0x14098f4d9  lea     rcx, [rsp+0F8h+var_C8]
0x14098f4de  call    BiReleasePrivilege
0x14098f4e3  test    ebx, ebx
0x14098f4e5  jns     short loc_14098F51E
0x14098f4e7  mov     [rsp+0F8h+arg_18], ebx
0x14098f4ee  mov     ecx, 2
0x14098f4f3  cmp     ebx, 0C0000022h
0x14098f4f9  cmovnz  ecx, r14d
0x14098f4fd  mov     dword ptr [rsp+0F8h+var_D0], ebx
0x14098f501  lea     rax, [r13+0Ch]
0x14098f505  mov     [rsp+0F8h+var_D8], rax
0x14098f50a  mov     r9d, r12d
0x14098f50d  mov     r8, r15
0x14098f510  lea     rdx, aFailedLoadKeyW; "Failed load key %ws. Flags: 0x%x File: "...
0x14098f517  call    BiLogMessage
0x14098f51c  jmp     short loc_14098F57E
0x14098f51e  lea     r8, [rsp+0F8h+ObjectAttributes]; ObjectAttributes
0x14098f523  mov     edx, 20019h; DesiredAccess
0x14098f528  mov     rcx, [rsp+0F8h+KeyHandle]; KeyHandle
0x14098f530  call    ZwOpenKey
0x14098f535  mov     ebx, eax
0x14098f537  mov     [rsp+0F8h+arg_18], eax
0x14098f53e  test    eax, eax
0x14098f540  jns     short loc_14098F57E
0x14098f542  lea     rdx, [rsp+0F8h+var_C8]
0x14098f547  mov     ecx, 11h
0x14098f54c  call    BiAcquirePrivilege
0x14098f551  lea     rcx, [rsp+0F8h+ObjectAttributes]
0x14098f556  call    ZwUnloadKey
0x14098f55b  lea     rcx, [rsp+0F8h+var_C8]
0x14098f560  call    BiReleasePrivilege
0x14098f565  mov     dword ptr [rsp+0F8h+var_D8], ebx
0x14098f569  mov     r9d, r12d
0x14098f56c  mov     r8, r15
0x14098f56f  lea     rdx, aFailedOpenNewl; "Failed open newly loaded key %ws. Flags"...
0x14098f576  mov     ecx, r14d
0x14098f579  call    BiLogMessage
0x14098f57e  test    rdi, rdi
0x14098f581  jz      short loc_14098F58B
0x14098f583  mov     rcx, rdi; Handle
0x14098f586  call    ZwClose
0x14098f58b  cmp     ebx, 0C000017Dh
0x14098f591  jnz     short loc_14098F5C8
0x14098f593  int     3; Trap to Debugger
0x14098f594  jmp     short loc_14098F5BC
0x14098f596  mov     esi, 5
0x14098f59b  lea     r14d, [rsi-1]
0x14098f59f  mov     r12d, 240h
0x14098f5a5  mov     r13, [rsp+0F8h+arg_8]
0x14098f5ad  mov     r15, [rsp+0F8h+arg_0]
0x14098f5b5  mov     ebx, [rsp+0F8h+arg_18]
0x14098f5bc  cmp     esi, 5
0x14098f5bf  jnb     short loc_14098F5C8
0x14098f5c1  inc     esi
0x14098f5c3  jmp     loc_14098F368
0x14098f5c8  mov     eax, ebx
0x14098f5ca  add     rsp, 0C0h
0x14098f5d1  pop     r15
0x14098f5d3  pop     r14
0x14098f5d5  pop     r13
0x14098f5d7  pop     r12
0x14098f5d9  pop     rdi
0x14098f5da  pop     rsi
0x14098f5db  pop     rbx
0x14098f5dc  retn
```
