# Microsoft::HostGuardian::Client::Plugin::CimUtilities::GetInstanceProperties(_MI_Instance const *,std::tuple<wchar_t const *,_MI_Type,uint,_MI_Value *> *,unsigned __int64)

- ea: `0x180009cfc`
- end: `0x180009e49`
- name: `?GetInstanceProperties@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEBU_MI_Instance@@PEAV?$tuple@PEB_WW4_MI_Type@@IPEAT_MI_Value@@@std@@_K@Z`
- size: `333`
- prototype: `void __fastcall(__int64, __int64, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180009070`
- `0x1800092fc`
- `0x1800096ec`
- `0x180009e50`

## callees

- `0x180009cfc`
- `0x180009f44`
- `0x18000a6b4`
- `0x18000c010`

## string_xrefs

- `0x180009dcd`: `servercommon\base\securehostingservice\common\service\plugin\cimutilities.cpp`
- `0x180009de9`: `servercommon\base\securehostingservice\common\service\plugin\cimutilities.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::CimUtilities::GetInstanceProperties(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3)
{
  __int64 v4; // rdi
  __int64 v6; // rsi
  int v7; // r15d
  const char *v8; // r14
  unsigned int v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // eax
  int v12; // [rsp+20h] [rbp-58h]
  int v13; // [rsp+20h] [rbp-58h]
  __int64 v14; // [rsp+38h] [rbp-40h]
  __int64 v15; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v17; // [rsp+90h] [rbp+18h] BYREF
  int v18; // [rsp+98h] [rbp+20h] BYREF

  if ( a3 )
  {
    v18 = 0;
    v4 = a2;
    v17 = 0x20000000;
    v6 = 0;
    while ( 1 )
    {
      v7 = *(_DWORD *)(32 * v6 + v4 + 16);
      v8 = *(const char **)(32 * v6 + v4 + 24);
      if ( !a1 || !*(_QWORD *)a1 )
        break;
      v9 = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, int *, int *, _QWORD))(*(_QWORD *)a1 + 88LL))(
             a1,
             v8,
             *(_QWORD *)(32 * v6 + v4),
             &v18,
             &v17,
             0);
      v10 = v9;
      if ( v9 || (v17 | 0x20000000) == 0x20000000 )
      {
        LOBYTE(a2) = 1;
        if ( v9 )
          goto LABEL_11;
      }
      else
      {
        LOBYTE(a2) = 0;
      }
      v11 = -2147467261;
LABEL_12:
      LOBYTE(v12) = a2;
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x71,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\cimutilities.cpp",
        (const char *)v11,
        v12,
        (bool)"Failed to get %ws",
        v8);
      LODWORD(v15) = v18;
      LODWORD(v14) = v7;
      LOBYTE(v13) = v18 != v7;
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x75,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\cimutilities.cpp",
        (const char *)0x8007070CLL,
        v13,
        (bool)"Unexpected output type for %ws Expected: %u, Actual: %u",
        v8,
        v14,
        v15);
      if ( ++v6 >= a3 )
        return;
    }
    v10 = 4;
    LOBYTE(a2) = 1;
LABEL_11:
    v11 = Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(
            (Microsoft::HostGuardian::Client::Plugin::CimUtilities *)v10,
            (enum _MI_Result)a2);
    goto LABEL_12;
  }
}

```

## disassembly

```asm
0x180009cfc  test    r8, r8
0x180009cff  jz      locret_180009E48
0x180009d05  mov     rax, rsp
0x180009d08  mov     [rax+8], rbx
0x180009d0c  push    rbp
0x180009d0d  push    rsi
0x180009d0e  push    rdi
0x180009d0f  push    r14
0x180009d11  push    r15
0x180009d13  sub     rsp, 50h
0x180009d17  mov     rbp, r8
0x180009d1a  mov     dword ptr [rax+20h], 0
0x180009d21  mov     rdi, rdx
0x180009d24  mov     dword ptr [rax+18h], 20000000h
0x180009d2b  mov     rbx, rcx
0x180009d2e  xor     esi, esi
0x180009d30  mov     r8, rsi
0x180009d33  shl     r8, 5
0x180009d37  mov     r15d, [r8+rdi+10h]
0x180009d3c  mov     r14, [r8+rdi+18h]
0x180009d41  test    rbx, rbx
0x180009d44  jz      short loc_180009DA8
0x180009d46  mov     rax, [rbx]
0x180009d49  test    rax, rax
0x180009d4c  jz      short loc_180009DA8
0x180009d4e  mov     r8, [r8+rdi]
0x180009d52  lea     rcx, [rsp+78h+arg_10]
0x180009d5a  mov     rax, [rax+58h]
0x180009d5e  lea     r9, [rsp+78h+arg_18]
0x180009d66  mov     qword ptr [rsp+78h+var_50], 0
0x180009d6f  mov     rdx, r14
0x180009d72  mov     qword ptr [rsp+78h+var_58], rcx
0x180009d77  mov     rcx, rbx
0x180009d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d7f  mov     ecx, eax
0x180009d81  test    eax, eax
0x180009d83  jnz     short loc_180009D9B
0x180009d85  mov     eax, [rsp+78h+arg_10]
0x180009d8c  bts     eax, 1Dh
0x180009d90  cmp     eax, 20000000h
0x180009d95  jz      short loc_180009D9B
0x180009d97  xor     edx, edx
0x180009d99  jmp     short loc_180009DA1
0x180009d9b  mov     dl, 1
0x180009d9d  test    ecx, ecx
0x180009d9f  jnz     short loc_180009DAF
0x180009da1  mov     eax, 80004003h
0x180009da6  jmp     short loc_180009DB4
0x180009da8  mov     ecx, 4; this
0x180009dad  mov     dl, 1; enum _MI_Result
0x180009daf  call    ?HRESULT_FROM_MIRESULT@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YAJW4_MI_Result@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::HRESULT_FROM_MIRESULT(_MI_Result)
0x180009db4  mov     rcx, [rsp+78h]; this
0x180009db9  lea     r8, aFailedToGetWs; "Failed to get %ws"
0x180009dc0  mov     [rsp+78h+var_48], r14; char *
0x180009dc5  mov     r9d, eax; char *
0x180009dc8  mov     qword ptr [rsp+78h+var_50], r8; bool
0x180009dcd  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x180009dd4  mov     byte ptr [rsp+78h+var_58], dl; int
0x180009dd8  mov     edx, 71h ; 'q'; void *
0x180009ddd  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180009de2  mov     eax, [rsp+78h+arg_18]
0x180009de9  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x180009df0  mov     rcx, [rsp+78h]; this
0x180009df5  cmp     eax, r15d
0x180009df8  mov     dword ptr [rsp+78h+var_38], eax
0x180009dfc  mov     r9d, 8007070Ch; char *
0x180009e02  mov     dword ptr [rsp+78h+var_40], r15d
0x180009e07  lea     rax, aUnexpectedOutp; "Unexpected output type for %ws Expected"...
0x180009e0e  setnz   dl
0x180009e11  mov     [rsp+78h+var_48], r14; char *
0x180009e16  mov     qword ptr [rsp+78h+var_50], rax; bool
0x180009e1b  mov     byte ptr [rsp+78h+var_58], dl; int
0x180009e1f  mov     edx, 75h ; 'u'; void *
0x180009e24  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180009e29  inc     rsi
0x180009e2c  cmp     rsi, rbp
0x180009e2f  jb      loc_180009D30
0x180009e35  mov     rbx, [rsp+78h+arg_0]
0x180009e3d  add     rsp, 50h
0x180009e41  pop     r15
0x180009e43  pop     r14
0x180009e45  pop     rdi
0x180009e46  pop     rsi
0x180009e47  pop     rbp
0x180009e48  retn
```
