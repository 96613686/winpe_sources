# CTscSettings::ChildDeviceHasClassGuid(ulong,_GUID)

- ea: `0x140033f78`
- end: `0x14003407f`
- name: `?ChildDeviceHasClassGuid@CTscSettings@@AEAAEKU_GUID@@@Z`
- size: `263`
- prototype: `unsigned __int8(CTscSettings *__hidden this, unsigned int, struct _GUID *__struct_ptr)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140033f78`
- `0x14003aaa8`
- `0x14003b2bc`

## callees

- `0x140033f78`
- `0x1401111b2`
- `0x140111220`

## import_xrefs

- `ole32!CLSIDFromString` at `0x140034027`
- `ole32!CLSIDFromString` at `0x140034027`
- `CFGMGR32!CM_Get_Child` at `0x140033fb7`
- `CFGMGR32!CM_Get_Child` at `0x140033fb7`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x140034008`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x140034008`
- `CFGMGR32!CM_Get_Sibling` at `0x140034051`
- `CFGMGR32!CM_Get_Sibling` at `0x140034051`

## pseudocode

```c
unsigned __int8 __fastcall CTscSettings::ChildDeviceHasClassGuid(CTscSettings *this, DEVINST a2, struct _GUID *a3)
{
  char v5; // bl
  CONFIGRET i; // eax
  DEVNODE pdnDevInst; // [rsp+30h] [rbp-39h] BYREF
  ULONG pulRegDataType; // [rsp+34h] [rbp-35h] BYREF
  ULONG pulLength; // [rsp+38h] [rbp-31h] BYREF
  GUID pclsid; // [rsp+40h] [rbp-29h] BYREF
  OLECHAR Buffer[40]; // [rsp+50h] [rbp-19h] BYREF

  pdnDevInst = 0;
  pulRegDataType = 0;
  v5 = 0;
  for ( i = CM_Get_Child(&pdnDevInst, a2, 0); !i; i = CM_Get_Sibling(&pdnDevInst, pdnDevInst, 0) )
  {
    pclsid = *a3;
    if ( !CTscSettings::ChildDeviceHasClassGuid(this, pdnDevInst, &pclsid) )
    {
      pulLength = 78;
      if ( CM_Get_DevNode_Registry_PropertyW(pdnDevInst, 9u, &pulRegDataType, Buffer, &pulLength, 0) )
        continue;
      if ( pulRegDataType != 1 )
        continue;
      pclsid = 0;
      if ( CLSIDFromString(Buffer, &pclsid) < 0 || memcmp_0(&pclsid, a3, 0x10u) )
        continue;
    }
    return 1;
  }
  return v5;
}

```

## disassembly

```asm
0x140033f78  mov     [rsp-8+arg_18], rbx
0x140033f7d  push    rbp
0x140033f7e  push    rsi
0x140033f7f  push    rdi
0x140033f80  lea     rbp, [rsp-47h]
0x140033f85  sub     rsp, 0B0h
0x140033f8c  mov     rax, cs:__security_cookie
0x140033f93  xor     rax, rsp
0x140033f96  mov     [rbp+57h+var_20], rax
0x140033f9a  mov     rdi, r8
0x140033f9d  mov     [rbp+57h+pdnDevInst], 0
0x140033fa4  mov     rsi, rcx
0x140033fa7  mov     [rbp+57h+pulRegDataType], 0
0x140033fae  xor     r8d, r8d; ulFlags
0x140033fb1  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x140033fb5  xor     bl, bl
0x140033fb7  call    cs:__imp_CM_Get_Child
0x140033fbd  test    eax, eax
0x140033fbf  jnz     loc_14003405E
0x140033fc5  movups  xmm0, xmmword ptr [rdi]
0x140033fc8  mov     edx, [rbp+57h+pdnDevInst]; unsigned int
0x140033fcb  lea     r8, [rbp+57h+pclsid]; struct _GUID
0x140033fcf  mov     rcx, rsi; this
0x140033fd2  movdqu  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x140033fd7  call    ?ChildDeviceHasClassGuid@CTscSettings@@AEAAEKU_GUID@@@Z; CTscSettings::ChildDeviceHasClassGuid(ulong,_GUID)
0x140033fdc  test    al, al
0x140033fde  jnz     short loc_14003405C
0x140033fe0  mov     ecx, [rbp+57h+pdnDevInst]; dnDevInst
0x140033fe3  lea     rax, [rbp+57h+var_88]
0x140033fe7  mov     [rsp+0C0h+ulFlags], 0; ulFlags
0x140033fef  lea     r9, [rbp+57h+Buffer]; Buffer
0x140033ff3  lea     r8, [rbp+57h+pulRegDataType]; pulRegDataType
0x140033ff7  mov     [rsp+0C0h+pulLength], rax; pulLength
0x140033ffc  mov     edx, 9; ulProperty
0x140034001  mov     [rbp+57h+var_88], 4Eh ; 'N'
0x140034008  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x14003400e  test    eax, eax
0x140034010  jnz     short loc_140034047
0x140034012  cmp     [rbp+57h+pulRegDataType], 1
0x140034016  jnz     short loc_140034047
0x140034018  xorps   xmm0, xmm0
0x14003401b  lea     rdx, [rbp+57h+pclsid]; pclsid
0x14003401f  lea     rcx, [rbp+57h+Buffer]; lpsz
0x140034023  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x140034027  call    cs:__imp_CLSIDFromString
0x14003402d  test    eax, eax
0x14003402f  js      short loc_140034047
0x140034031  mov     r8d, 10h; Size
0x140034037  lea     rcx, [rbp+57h+pclsid]; Buf1
0x14003403b  mov     rdx, rdi; Buf2
0x14003403e  call    memcmp_0
0x140034043  test    eax, eax
0x140034045  jz      short loc_14003405C
0x140034047  mov     edx, [rbp+57h+pdnDevInst]; dnDevInst
0x14003404a  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x14003404e  xor     r8d, r8d; ulFlags
0x140034051  call    cs:__imp_CM_Get_Sibling
0x140034057  jmp     loc_140033FBD
0x14003405c  mov     bl, 1
0x14003405e  mov     al, bl
0x140034060  mov     rcx, [rbp+57h+var_20]
0x140034064  xor     rcx, rsp; StackCookie
0x140034067  call    __security_check_cookie
0x14003406c  mov     rbx, [rsp+0C0h+arg_18]
0x140034074  add     rsp, 0B0h
0x14003407b  pop     rdi
0x14003407c  pop     rsi
0x14003407d  pop     rbp
0x14003407e  retn
```
