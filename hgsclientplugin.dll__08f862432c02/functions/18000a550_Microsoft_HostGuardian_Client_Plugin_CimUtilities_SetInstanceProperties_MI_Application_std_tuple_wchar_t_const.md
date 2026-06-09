# Microsoft::HostGuardian::Client::Plugin::CimUtilities::SetInstanceProperties(_MI_Application &,std::tuple<wchar_t const *,_MI_Type,uint,_MI_Value *> *,unsigned __int64)

- ea: `0x18000a550`
- end: `0x18000a6ac`
- name: `?SetInstanceProperties@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_MI_Instance@@P6A?AW4_MI_Result@@PEAU1@@Z$1?MI_Instance_Delete_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW42@0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAU_MI_Application@@PEAV?$tuple@PEB_WW4_MI_Type@@IPEAT_MI_Value@@@std@@_K@Z`
- size: `348`
- prototype: `__int64 *__fastcall(__int64 *, enum _MI_Result, __int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180009070`
- `0x1800092fc`
- `0x1800096ec`

## callees

- `0x180009a84`
- `0x180009f44`
- `0x18000a550`
- `0x18000c010`

## string_xrefs

- `0x18000a658`: `servercommon\base\securehostingservice\common\service\plugin\cimutilities.cpp`
- `0x18000a685`: `servercommon\base\securehostingservice\common\service\plugin\cimutilities.cpp`
- `0x18000a69a`: `servercommon\base\securehostingservice\common\service\plugin\cimutilities.cpp`

## pseudocode

```c
__int64 *__fastcall Microsoft::HostGuardian::Client::Plugin::CimUtilities::SetInstanceProperties(
        __int64 *a1,
        enum _MI_Result a2,
        __int64 a3,
        unsigned __int64 a4)
{
  unsigned int v7; // edi
  __int64 v8; // rsi
  __int64 v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v13; // eax
  int v14; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a1 = 0;
  if ( !a3 )
    return a1;
  *a1 = 0;
  if ( !miApplication.ft )
  {
    *a1 = 0;
    v7 = 4;
LABEL_17:
    v13 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(
            (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)v7,
            a2);
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      137,
      (__int64)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\cimutilities.cpp",
      (const char *)v13,
      v14);
  }
  v7 = ((__int64 (__fastcall *)(MI_Application *, const wchar_t *, _QWORD, __int64 *))miApplication.ft->NewInstance)(
         &miApplication,
         L"__parameters",
         0,
         a1);
  if ( v7 )
    goto LABEL_17;
  if ( !*a1 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      138,
      (__int64)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\cimutilities.cpp",
      (const char *)0x80004003LL,
      v14);
  v8 = 0;
  if ( a4 )
  {
    while ( 1 )
    {
      v9 = *a1;
      if ( !*a1 || !*(_QWORD *)v9 )
        break;
      v14 = *(_DWORD *)(32 * v8 + a3 + 8);
      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v9 + 64LL))(
              v9,
              *(_QWORD *)(32 * v8 + a3 + 24),
              *(_QWORD *)(32 * v8 + a3),
              *(unsigned int *)(32 * v8 + a3 + 16));
      if ( v10 )
        goto LABEL_11;
      LOBYTE(a2) = 0;
LABEL_12:
      v11 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(
              (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)v10,
              a2);
      if ( (_BYTE)a2 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          153,
          (__int64)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\cimutilities.cpp",
          (const char *)v11,
          v14);
      if ( ++v8 >= a4 )
        return a1;
    }
    v10 = 4;
LABEL_11:
    LOBYTE(a2) = 1;
    goto LABEL_12;
  }
  return a1;
}

```

## disassembly

```asm
0x18000a550  mov     rax, rsp
0x18000a553  mov     [rax+10h], rbx
0x18000a557  mov     [rax+18h], rbp
0x18000a55b  mov     [rax+8], rcx
0x18000a55f  push    rsi
0x18000a560  push    rdi
0x18000a561  push    r14
0x18000a563  sub     rsp, 40h
0x18000a567  mov     rbp, r9
0x18000a56a  mov     r14, r8
0x18000a56d  mov     rbx, rcx
0x18000a570  mov     dword ptr [rax-28h], 0
0x18000a577  mov     qword ptr [rcx], 0
0x18000a57e  mov     dword ptr [rax-28h], 1
0x18000a585  test    r8, r8
0x18000a588  jz      loc_18000A637
0x18000a58e  mov     qword ptr [rcx], 0
0x18000a595  mov     rax, cs:?miApplication@@3U_MI_Application@@A.ft; _MI_Application miApplication ...
0x18000a59c  test    rax, rax
0x18000a59f  jz      loc_18000A66A
0x18000a5a5  mov     r9, rcx
0x18000a5a8  xor     r8d, r8d
0x18000a5ab  lea     rdx, aParameters; "__parameters"
0x18000a5b2  lea     rcx, ?miApplication@@3U_MI_Application@@A; _MI_Application miApplication
0x18000a5b9  mov     rax, [rax+18h]
0x18000a5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5c2  mov     edi, eax
0x18000a5c4  test    eax, eax
0x18000a5c6  jnz     loc_18000A676
0x18000a5cc  cmp     qword ptr [rbx], 0
0x18000a5d0  jz      short loc_18000A64D
0x18000a5d2  xor     esi, esi
0x18000a5d4  test    rbp, rbp
0x18000a5d7  jz      short loc_18000A637
0x18000a5d9  lea     edi, [rax+4]
0x18000a5dc  mov     rcx, [rbx]
0x18000a5df  test    rcx, rcx
0x18000a5e2  jz      short loc_18000A61B
0x18000a5e4  mov     r10, [rcx]
0x18000a5e7  test    r10, r10
0x18000a5ea  jz      short loc_18000A61B
0x18000a5ec  mov     rax, rsi
0x18000a5ef  shl     rax, 5
0x18000a5f3  mov     edx, [rax+r14+8]
0x18000a5f8  mov     [rsp+58h+var_38], edx
0x18000a5fc  mov     r9d, [rax+r14+10h]
0x18000a601  mov     r8, [rax+r14]
0x18000a605  mov     rdx, [rax+r14+18h]
0x18000a60a  mov     rax, [r10+40h]
0x18000a60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a613  test    eax, eax
0x18000a615  jnz     short loc_18000A61D
0x18000a617  xor     dl, dl
0x18000a619  jmp     short loc_18000A61F
0x18000a61b  mov     eax, edi
0x18000a61d  mov     dl, 1; enum _MI_Result
0x18000a61f  mov     ecx, eax; this
0x18000a621  call    ?HRESULT_FROM_MIRESULT@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJW4_MI_Result@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(_MI_Result)
0x18000a626  mov     rcx, [rsp+58h]; this
0x18000a62b  test    dl, dl
0x18000a62d  jnz     short loc_18000A697
0x18000a62f  inc     rsi
0x18000a632  cmp     rsi, rbp
0x18000a635  jb      short loc_18000A5DC
0x18000a637  mov     rax, rbx
0x18000a63a  mov     rbx, [rsp+58h+arg_8]
0x18000a63f  mov     rbp, [rsp+58h+arg_10]
0x18000a644  add     rsp, 40h
0x18000a648  pop     r14
0x18000a64a  pop     rdi
0x18000a64b  pop     rsi
0x18000a64c  retn
0x18000a64d  mov     rcx, [rsp+58h]; this
0x18000a652  mov     r9d, 80004003h; char *
0x18000a658  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x18000a65f  mov     edx, 8Ah; void *
0x18000a664  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a66a  mov     qword ptr [rcx], 0
0x18000a671  mov     edi, 4
0x18000a676  mov     ecx, edi; this
0x18000a678  call    ?HRESULT_FROM_MIRESULT@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJW4_MI_Result@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(_MI_Result)
0x18000a67d  mov     r9d, eax; char *
0x18000a680  mov     rcx, [rsp+58h]; this
0x18000a685  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x18000a68c  mov     edx, 89h; void *
0x18000a691  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000a697  mov     r9d, eax; char *
0x18000a69a  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x18000a6a1  mov     edx, 99h; void *
0x18000a6a6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
