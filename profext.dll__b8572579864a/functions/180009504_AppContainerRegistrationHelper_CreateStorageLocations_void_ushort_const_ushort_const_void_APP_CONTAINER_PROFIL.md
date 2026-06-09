# AppContainerRegistrationHelper::CreateStorageLocations(void *,ushort const *,ushort const *,void *,APP_CONTAINER_PROFILE_TYPE,unsigned __int64,_GUID const *,ushort *)

- ea: `0x180009504`
- end: `0x18000985a`
- name: `?CreateStorageLocations@AppContainerRegistrationHelper@@CAJPEAXPEBG10W4APP_CONTAINER_PROFILE_TYPE@@_KPEBU_GUID@@PEAG@Z`
- size: `854`
- prototype: `static int __high(void *, const unsigned __int16 *, const unsigned __int16 *, void *, enum APP_CONTAINER_PROFILE_TYPE, unsigned __int64, const struct _GUID *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d980`

## callees

- `0x180003c00`
- `0x1800040c0`
- `0x1800044e0`
- `0x180004594`
- `0x180009504`
- `0x180009860`
- `0x18000f614`
- `0x180014480`
- `0x180014d5c`
- `0x1800153b8`
- `0x180015fe0`
- `0x180016554`

## string_xrefs

- `0x180009589`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000960e`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180009698`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800096ec`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000974a`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180009791`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800097d1`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180009831`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x18000968d`: `Name %ls Sid %ls type %d`
- `0x18000973f`: `Name %ls Sid %ls type %d`
- `0x180009575`: `Name %ls Sid %ls`
- `0x18000963a`: `Name %ws Sid %ws`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::CreateStorageLocations(
        void *a1,
        char *a2,
        const unsigned __int16 *a3,
        void *a4,
        int a5,
        __int64 a6,
        struct _GUID *a7,
        unsigned __int16 *a8)
{
  int v11; // r12d
  int v12; // eax
  int RegistryStorage; // r15d
  const char *v14; // rax
  __int64 v15; // rdx
  __int64 result; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int ChildStateLocations; // eax
  int v20; // r15d
  unsigned int v21; // eax
  unsigned int v22; // eax
  int v23; // eax
  unsigned int v24; // ebx
  int v25; // [rsp+20h] [rbp-68h]
  unsigned __int16 *v26; // [rsp+30h] [rbp-58h]
  __int64 v27; // [rsp+38h] [rbp-50h]
  __int64 v28; // [rsp+38h] [rbp-50h]
  __int64 v29; // [rsp+38h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( (unsigned int)(a5 - 1) <= 2 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    if ( !a1 )
    {
      v12 = AppContainerRegistrationHelper::EnsureAppContainerParentFolder(a2, a7);
      RegistryStorage = AppContainerRegistrationHelper::SetAPIContextIfFailed(v12, 0x58Au, a3, 0x208u, a8);
      if ( RegistryStorage < 0 )
      {
        v14 = "Name %ls Sid %ls";
        v15 = 1418;
LABEL_5:
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)v15,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)RegistryStorage,
          (int)v14,
          a2,
          a3);
        return (unsigned int)RegistryStorage;
      }
    }
  }
  RegistryStorage = AppContainerRegistrationHelper::CreateRegistryStorage(a1, a2, a3, a4, 0x208u, a7, a8);
  if ( RegistryStorage >= 0 )
  {
    RegistryStorage = AppContainerRegistrationHelper::CreateKnownFolders(a1, a2, a4, a5, a7);
    if ( RegistryStorage >= 0 )
    {
      if ( !a1 )
        return 0;
      ChildStateLocations = AppContainerRegistrationHelper::CreateChildStateLocations(a1, a4, a2, a5, a7);
      v20 = wil::details::in1diag3::Log_IfFailedMsg(
              retaddr,
              (void *)0x5BD,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
              (const char *)ChildStateLocations,
              (__int64)"Name %ls Sid %ls type %d",
              a2,
              a3,
              a5);
      if ( v20 >= 0 )
        return 0;
      v21 = AppContainerRegistrationHelper::DeleteAppContainerRootFolder((__int64)a1, a2, a5, a7);
      LODWORD(v28) = a5;
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x5C2,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v21,
        (__int64)"Name %ls Sid %ls type %d",
        a2,
        a3,
        v28);
      v22 = AppContainerRegistrationHelper::DeleteRegistryStorage(a1, (const unsigned __int16 *)a2, a3, a7);
      LODWORD(v29) = a5;
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x5C4,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v22,
        (__int64)"Name %ls Sid %ls type %d",
        a2,
        a3,
        v29);
      if ( v20 == -2147024891 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v23 = AppContainerRegistrationHelper::SetAPIContextIfFailed(v20, 0x5C9u, a3, 0x208u, a8);
      v24 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C9,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)v23,
          v25);
        return v24;
      }
      else
      {
        return 0;
      }
    }
    else
    {
      v18 = AppContainerRegistrationHelper::DeleteRegistryStorage(a1, (const unsigned __int16 *)a2, a3, a7);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x5AD,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v18,
        (__int64)"Name %ls Sid %ls type %d",
        a2,
        a3,
        a5);
      AppContainerRegistrationHelper::SetAPIContextIfFailed(RegistryStorage, 0x5AEu, a3, 0x208u, a8);
      result = 2147942403LL;
      if ( RegistryStorage != -2147024893 )
      {
        LODWORD(v27) = a5;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x5B2,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
          (const char *)(unsigned int)RegistryStorage,
          (int)"Name %ls Sid %ls type %d",
          a2,
          a3,
          v27);
        return (unsigned int)RegistryStorage;
      }
    }
  }
  else
  {
    if ( !v11 )
    {
      v17 = AppContainerRegistrationHelper::DeleteAppContainerRootFolder((__int64)a1, a2, a5, a7);
      LODWORD(v26) = a5;
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x59B,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
        (const char *)v17,
        (__int64)"Name %ls type %d",
        a2,
        v26);
    }
    result = 2147943418LL;
    if ( RegistryStorage != -2147023878 )
    {
      v14 = "Name %ws Sid %ws";
      v15 = 1439;
      goto LABEL_5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009504  mov     [rsp+arg_18], r9
0x180009509  push    rbx
0x18000950a  push    rbp
0x18000950b  push    rsi
0x18000950c  push    rdi
0x18000950d  push    r12
0x18000950f  push    r13
0x180009511  push    r14
0x180009513  push    r15
0x180009515  sub     rsp, 48h
0x180009519  mov     esi, [rsp+88h+arg_20]
0x180009520  mov     rdi, r8
0x180009523  mov     r13, [rsp+88h+arg_38]
0x18000952b  mov     rbx, rdx
0x18000952e  mov     r14, [rsp+88h+arg_30]
0x180009536  mov     rbp, rcx
0x180009539  lea     eax, [rsi-1]
0x18000953c  cmp     eax, 2
0x18000953f  jbe     short loc_1800095AF
0x180009541  xor     r12d, r12d
0x180009544  test    rcx, rcx
0x180009547  jnz     short loc_1800095B5
0x180009549  mov     rdx, r14; struct _GUID *
0x18000954c  mov     rcx, rbx; char *
0x18000954f  call    ?EnsureAppContainerParentFolder@AppContainerRegistrationHelper@@CAJPEBGPEBU_GUID@@@Z; AppContainerRegistrationHelper::EnsureAppContainerParentFolder(ushort const *,_GUID const *)
0x180009554  mov     ecx, eax; int
0x180009556  mov     [rsp+88h+var_68], r13; unsigned __int16 *
0x18000955b  mov     r9d, 208h; unsigned __int64
0x180009561  mov     r8, rdi; unsigned __int16 *
0x180009564  mov     edx, 58Ah; unsigned int
0x180009569  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x18000956e  mov     r15d, eax
0x180009571  test    eax, eax
0x180009573  jns     short loc_1800095B5
0x180009575  lea     rax, aNameLsSidLs; "Name %ls Sid %ls"
0x18000957c  mov     edx, 58Ah; void *
0x180009581  mov     rcx, [rsp+88h]; this
0x180009589  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009590  mov     [rsp+88h+var_58], rdi
0x180009595  mov     r9d, r15d; char *
0x180009598  mov     [rsp+88h+var_60], rbx; char *
0x18000959d  mov     [rsp+88h+var_68], rax; int
0x1800095a2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800095a7  mov     eax, r15d
0x1800095aa  jmp     loc_180009848
0x1800095af  mov     r12d, 1
0x1800095b5  mov     r9, [rsp+88h+arg_18]; void *
0x1800095bd  mov     r8, rdi; unsigned __int16 *
0x1800095c0  mov     [rsp+88h+var_58], r13; unsigned __int16 *
0x1800095c5  mov     rdx, rbx; unsigned __int16 *
0x1800095c8  mov     [rsp+88h+var_60], r14; struct _GUID *
0x1800095cd  mov     rcx, rbp; void *
0x1800095d0  mov     [rsp+88h+var_68], 208h; unsigned __int64
0x1800095d9  call    ?CreateRegistryStorage@AppContainerRegistrationHelper@@CAJPEAXPEBG10_KPEBU_GUID@@PEAG@Z; AppContainerRegistrationHelper::CreateRegistryStorage(void *,ushort const *,ushort const *,void *,unsigned __int64,_GUID const *,ushort *)
0x1800095de  mov     r15d, eax
0x1800095e1  test    eax, eax
0x1800095e3  jns     short loc_18000964B
0x1800095e5  test    r12d, r12d
0x1800095e8  jnz     short loc_18000962C
0x1800095ea  mov     r9, r14
0x1800095ed  mov     r8d, esi
0x1800095f0  mov     rdx, rbx
0x1800095f3  mov     rcx, rbp
0x1800095f6  call    ?DeleteAppContainerRootFolder@AppContainerRegistrationHelper@@CAJPEAXPEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteAppContainerRootFolder(void *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x1800095fb  mov     rcx, [rsp+88h]; this
0x180009603  lea     rdx, aNameLsTypeD; "Name %ls type %d"
0x18000960a  mov     dword ptr [rsp+88h+var_58], esi
0x18000960e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009615  mov     [rsp+88h+var_60], rbx; char *
0x18000961a  mov     r9d, eax; char *
0x18000961d  mov     [rsp+88h+var_68], rdx; __int64
0x180009622  mov     edx, 59Bh; void *
0x180009627  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000962c  mov     eax, 800703FAh
0x180009631  cmp     r15d, eax
0x180009634  jz      loc_180009848
0x18000963a  lea     rax, aNameWsSidWs; "Name %ws Sid %ws"
0x180009641  mov     edx, 59Fh
0x180009646  jmp     loc_180009581
0x18000964b  mov     r12, [rsp+88h+arg_18]
0x180009653  mov     r9d, esi
0x180009656  mov     r8, r12
0x180009659  mov     [rsp+88h+var_68], r14
0x18000965e  mov     rdx, rbx
0x180009661  mov     rcx, rbp
0x180009664  call    ?CreateKnownFolders@AppContainerRegistrationHelper@@CAJPEAXPEBG0W4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::CreateKnownFolders(void *,ushort const *,void *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x180009669  mov     r15d, eax
0x18000966c  test    eax, eax
0x18000966e  jns     loc_180009718
0x180009674  mov     r9, r14; struct _GUID *
0x180009677  mov     r8, rdi; unsigned __int16 *
0x18000967a  mov     rdx, rbx; unsigned __int16 *
0x18000967d  mov     rcx, rbp; void *
0x180009680  call    ?DeleteRegistryStorage@AppContainerRegistrationHelper@@CAJPEAXPEBG1PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteRegistryStorage(void *,ushort const *,ushort const *,_GUID const *)
0x180009685  mov     rcx, [rsp+88h]; this
0x18000968d  lea     r12, aNameLsSidLsTyp; "Name %ls Sid %ls type %d"
0x180009694  mov     dword ptr [rsp+88h+var_50], esi
0x180009698  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000969f  mov     [rsp+88h+var_58], rdi
0x1800096a4  mov     r9d, eax; char *
0x1800096a7  mov     [rsp+88h+var_60], rbx; char *
0x1800096ac  mov     edx, 5ADh; void *
0x1800096b1  mov     [rsp+88h+var_68], r12; __int64
0x1800096b6  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800096bb  mov     r9d, 208h; unsigned __int64
0x1800096c1  mov     [rsp+88h+var_68], r13; unsigned __int16 *
0x1800096c6  mov     r8, rdi; unsigned __int16 *
0x1800096c9  mov     edx, 5AEh; unsigned int
0x1800096ce  mov     ecx, r15d; int
0x1800096d1  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x1800096d6  mov     eax, 80070003h
0x1800096db  cmp     r15d, eax
0x1800096de  jz      loc_180009848
0x1800096e4  mov     rcx, [rsp+88h]; this
0x1800096ec  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800096f3  mov     dword ptr [rsp+88h+var_50], esi
0x1800096f7  mov     r9d, r15d; char *
0x1800096fa  mov     [rsp+88h+var_58], rdi
0x1800096ff  mov     edx, 5B2h; void *
0x180009704  mov     [rsp+88h+var_60], rbx; char *
0x180009709  mov     [rsp+88h+var_68], r12; int
0x18000970e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180009713  jmp     loc_1800095A7
0x180009718  test    rbp, rbp
0x18000971b  jz      loc_180009846
0x180009721  mov     r9d, esi
0x180009724  mov     [rsp+88h+var_68], r14
0x180009729  mov     r8, rbx
0x18000972c  mov     rdx, r12
0x18000972f  mov     rcx, rbp
0x180009732  call    ?CreateChildStateLocations@AppContainerRegistrationHelper@@CAJPEAX0PEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::CreateChildStateLocations(void *,void *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x180009737  mov     rcx, [rsp+88h]; this
0x18000973f  lea     r12, aNameLsSidLsTyp; "Name %ls Sid %ls type %d"
0x180009746  mov     dword ptr [rsp+88h+var_50], esi
0x18000974a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009751  mov     [rsp+88h+var_58], rdi
0x180009756  mov     r9d, eax; char *
0x180009759  mov     [rsp+88h+var_60], rbx; char *
0x18000975e  mov     edx, 5BDh; void *
0x180009763  mov     [rsp+88h+var_68], r12; __int64
0x180009768  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000976d  mov     r15d, eax
0x180009770  test    eax, eax
0x180009772  jns     loc_180009846
0x180009778  mov     r9, r14
0x18000977b  mov     r8d, esi
0x18000977e  mov     rdx, rbx
0x180009781  mov     rcx, rbp
0x180009784  call    ?DeleteAppContainerRootFolder@AppContainerRegistrationHelper@@CAJPEAXPEBGW4APP_CONTAINER_PROFILE_TYPE@@PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteAppContainerRootFolder(void *,ushort const *,APP_CONTAINER_PROFILE_TYPE,_GUID const *)
0x180009789  mov     rcx, [rsp+88h]; this
0x180009791  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009798  mov     dword ptr [rsp+88h+var_50], esi
0x18000979c  mov     r9d, eax; char *
0x18000979f  mov     [rsp+88h+var_58], rdi
0x1800097a4  mov     edx, 5C2h; void *
0x1800097a9  mov     [rsp+88h+var_60], rbx; char *
0x1800097ae  mov     [rsp+88h+var_68], r12; __int64
0x1800097b3  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800097b8  mov     r9, r14; struct _GUID *
0x1800097bb  mov     r8, rdi; unsigned __int16 *
0x1800097be  mov     rdx, rbx; unsigned __int16 *
0x1800097c1  mov     rcx, rbp; void *
0x1800097c4  call    ?DeleteRegistryStorage@AppContainerRegistrationHelper@@CAJPEAXPEBG1PEBU_GUID@@@Z; AppContainerRegistrationHelper::DeleteRegistryStorage(void *,ushort const *,ushort const *,_GUID const *)
0x1800097c9  mov     rcx, [rsp+88h]; this
0x1800097d1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800097d8  mov     dword ptr [rsp+88h+var_50], esi
0x1800097dc  mov     r9d, eax; char *
0x1800097df  mov     [rsp+88h+var_58], rdi
0x1800097e4  mov     edx, 5C4h; void *
0x1800097e9  mov     [rsp+88h+var_60], rbx; char *
0x1800097ee  mov     [rsp+88h+var_68], r12; __int64
0x1800097f3  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800097f8  cmp     r15d, 80070005h
0x1800097ff  jnz     short loc_180009806
0x180009801  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180009806  mov     r8, rdi; unsigned __int16 *
0x180009809  mov     [rsp+88h+var_68], r13; int
0x18000980e  mov     edi, 5C9h
0x180009813  mov     r9d, 208h; unsigned __int64
0x180009819  mov     edx, edi; unsigned int
0x18000981b  mov     ecx, r15d; int
0x18000981e  call    ?SetAPIContextIfFailed@AppContainerRegistrationHelper@@SAJJIPEBG_KPEAG@Z; AppContainerRegistrationHelper::SetAPIContextIfFailed(long,uint,ushort const *,unsigned __int64,ushort *)
0x180009823  mov     ebx, eax
0x180009825  test    eax, eax
0x180009827  jns     short loc_180009846
0x180009829  mov     rcx, [rsp+88h]; this
0x180009831  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009838  mov     r9d, eax; char *
0x18000983b  mov     edx, edi; void *
0x18000983d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009842  mov     eax, ebx
0x180009844  jmp     short loc_180009848
0x180009846  xor     eax, eax
0x180009848  add     rsp, 48h
0x18000984c  pop     r15
0x18000984e  pop     r14
0x180009850  pop     r13
0x180009852  pop     r12
0x180009854  pop     rdi
0x180009855  pop     rsi
0x180009856  pop     rbp
0x180009857  pop     rbx
0x180009858  retn
```
