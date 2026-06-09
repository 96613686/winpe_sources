# DevUtilsGetConfigFlags

- ea: `0x1800096a8`
- end: `0x180009734`
- name: `DevUtilsGetConfigFlags`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009bf0`

## callees

- `0x1800096a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009721`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009721`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Registry_PropertyW` at `0x1800096ef`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Registry_PropertyW` at `0x1800096ef`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180009700`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180009700`

## pseudocode

```c
_BOOL8 __fastcall DevUtilsGetConfigFlags(DEVINST a1, void *a2)
{
  DWORD v2; // ebx
  CONFIGRET DevNode_Registry_PropertyW; // eax
  ULONG pulLength; // [rsp+48h] [rbp+10h] BYREF
  ULONG pulRegDataType; // [rsp+50h] [rbp+18h] BYREF

  pulRegDataType = 0;
  pulLength = 0;
  if ( a2 )
  {
    pulLength = 4;
    DevNode_Registry_PropertyW = CM_Get_DevNode_Registry_PropertyW(a1, 0xBu, &pulRegDataType, a2, &pulLength, 0);
    if ( DevNode_Registry_PropertyW )
    {
      v2 = CM_MapCrToWin32Err(DevNode_Registry_PropertyW, 0xDu);
    }
    else if ( pulRegDataType != 4 || (v2 = 0, pulLength != 4) )
    {
      v2 = 13;
    }
  }
  else
  {
    v2 = 87;
  }
  SetLastError(v2);
  return v2 == 0;
}

```

## disassembly

```asm
0x1800096a8  push    rbx
0x1800096aa  sub     rsp, 30h
0x1800096ae  mov     [rsp+38h+pulRegDataType], 0
0x1800096b6  mov     [rsp+38h+arg_8], 0
0x1800096be  test    rdx, rdx
0x1800096c1  jnz     short loc_1800096C8
0x1800096c3  lea     ebx, [rdx+57h]
0x1800096c6  jmp     short loc_18000971F
0x1800096c8  lea     rax, [rsp+38h+arg_8]
0x1800096cd  mov     [rsp+38h+ulFlags], 0; ulFlags
0x1800096d5  mov     r9, rdx; Buffer
0x1800096d8  mov     [rsp+38h+pulLength], rax; pulLength
0x1800096dd  mov     edx, 0Bh; ulProperty
0x1800096e2  mov     [rsp+38h+arg_8], 4
0x1800096ea  lea     r8, [rsp+38h+pulRegDataType]; pulRegDataType
0x1800096ef  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x1800096f5  test    eax, eax
0x1800096f7  jz      short loc_18000970A
0x1800096f9  mov     edx, 0Dh; DefaultErr
0x1800096fe  mov     ecx, eax; CmReturnCode
0x180009700  call    cs:__imp_CM_MapCrToWin32Err
0x180009706  mov     ebx, eax
0x180009708  jmp     short loc_18000971F
0x18000970a  cmp     [rsp+38h+pulRegDataType], 4
0x18000970f  jnz     short loc_18000971A
0x180009711  xor     ebx, ebx
0x180009713  cmp     [rsp+38h+arg_8], 4
0x180009718  jz      short loc_18000971F
0x18000971a  mov     ebx, 0Dh
0x18000971f  mov     ecx, ebx; dwErrCode
0x180009721  call    cs:__imp_SetLastError
0x180009727  xor     eax, eax
0x180009729  test    ebx, ebx
0x18000972b  setz    al
0x18000972e  add     rsp, 30h
0x180009732  pop     rbx
0x180009733  retn
```
