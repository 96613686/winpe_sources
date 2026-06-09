# AppContainerRegistrationHelper::DeleteStorageLocations(void *,ushort const *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)

- ea: `0x180016644`
- end: `0x180016737`
- name: `?DeleteStorageLocations@AppContainerRegistrationHelper@@CAJPEAXPEBG1W4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009a34`
- `0x1800162d0`

## callees

- `0x1800044e0`
- `0x180015fe0`
- `0x180016554`
- `0x180016644`

## string_xrefs

- `0x1800166cb`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180016707`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800166bf`: `Name %ls Sid %ls type %d`
- `0x1800166fb`: `Name %ls Sid %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppContainerRegistrationHelper::DeleteStorageLocations(
        void *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        struct _GUID *a5)
{
  int v9; // edi
  int v10; // ebx
  __int64 result; // rax
  int v12; // [rsp+38h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v9 = AppContainerRegistrationHelper::DeleteAppContainerRootFolder(a1, a2, a4, a5);
  v10 = AppContainerRegistrationHelper::DeleteRegistryStorage(a1, a2, a3, a5);
  result = 2147942402LL;
  if ( v9 != -2147024894 && v10 != -2147024894 && v9 != -2147024893 )
  {
    if ( v9 >= 0 )
    {
      if ( v10 >= 0 )
      {
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x5E4,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)v10,
          (int)"Name %ls Sid %ls",
          (const char *)a2,
          a3);
        return (unsigned int)v10;
      }
    }
    else
    {
      if ( v9 != -2147024891 && v9 != -2147024864 )
      {
        v12 = a4;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x5E3,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)v9,
          (int)"Name %ls Sid %ls type %d",
          (const char *)a2,
          a3,
          v12);
      }
      return (unsigned int)v9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016644  push    rbx
0x180016646  push    rbp
0x180016647  push    rsi
0x180016648  push    rdi
0x180016649  push    r14
0x18001664b  sub     rsp, 40h
0x18001664f  mov     r14d, r9d
0x180016652  mov     rbp, r8
0x180016655  mov     r9, [rsp+68h+arg_20]
0x18001665d  mov     r8d, r14d
0x180016660  mov     rsi, rdx
0x180016663  mov     rbx, rcx
0x180016666  call    ?DeleteAppContainerRootFolder@AppContainerRegistrationHelper@@CAJPEAXPEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteAppContainerRootFolder(void *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x18001666b  mov     r9, [rsp+68h+arg_20]; struct _GUID *
0x180016673  mov     r8, rbp; unsigned __int16 *
0x180016676  mov     rdx, rsi; unsigned __int16 *
0x180016679  mov     rcx, rbx; void *
0x18001667c  mov     edi, eax
0x18001667e  call    ?DeleteRegistryStorage@AppContainerRegistrationHelper@@CAJPEAXPEBG1PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteRegistryStorage(void *,ushort const *,ushort const *,_GUID const *)
0x180016683  mov     ebx, eax
0x180016685  mov     eax, 80070002h
0x18001668a  cmp     edi, eax
0x18001668c  jz      loc_18001672B
0x180016692  cmp     ebx, eax
0x180016694  jz      loc_18001672B
0x18001669a  cmp     edi, 80070003h
0x1800166a0  jz      loc_18001672B
0x1800166a6  test    edi, edi
0x1800166a8  jns     short loc_1800166F2
0x1800166aa  cmp     edi, 80070005h
0x1800166b0  jz      short loc_1800166EE
0x1800166b2  cmp     edi, 80070020h
0x1800166b8  jz      short loc_1800166EE
0x1800166ba  mov     rcx, [rsp+68h]; this
0x1800166bf  lea     rax, aNameLsSidLsTyp; "Name %ls Sid %ls type %d"
0x1800166c6  mov     [rsp+68h+var_30], r14d
0x1800166cb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800166d2  mov     [rsp+68h+var_38], rbp
0x1800166d7  mov     r9d, edi; char *
0x1800166da  mov     [rsp+68h+var_40], rsi; char *
0x1800166df  mov     edx, 5E3h; void *
0x1800166e4  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800166e9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800166ee  mov     eax, edi
0x1800166f0  jmp     short loc_18001672B
0x1800166f2  test    ebx, ebx
0x1800166f4  jns     short loc_180016729
0x1800166f6  mov     rcx, [rsp+68h]; this
0x1800166fb  lea     rax, aNameLsSidLs; "Name %ls Sid %ls"
0x180016702  mov     [rsp+68h+var_38], rbp
0x180016707  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001670e  mov     [rsp+68h+var_40], rsi; char *
0x180016713  mov     r9d, ebx; char *
0x180016716  mov     edx, 5E4h; void *
0x18001671b  mov     qword ptr [rsp+68h+var_48], rax; int
0x180016720  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180016725  mov     eax, ebx
0x180016727  jmp     short loc_18001672B
0x180016729  xor     eax, eax
0x18001672b  add     rsp, 40h
0x18001672f  pop     r14
0x180016731  pop     rdi
0x180016732  pop     rsi
0x180016733  pop     rbp
0x180016734  pop     rbx
0x180016735  retn
```
