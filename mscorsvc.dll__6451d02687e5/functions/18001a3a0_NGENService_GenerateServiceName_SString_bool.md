# NGENService::GenerateServiceName(SString &,bool)

- ea: `0x18001a3a0`
- end: `0x18001a68d`
- name: `?GenerateServiceName@NGENService@@YAJAEAVSString@@_N@Z`
- size: `749`
- prototype: `__int64 __fastcall(NGENService *__hidden this, struct SString *, bool)`
- caller_count: `5`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18001a690`
- `0x18001ae6c`
- `0x18001b128`
- `0x18001b9d0`
- `0x18001bcfc`

## callees

- `0x180001de0`
- `0x180001e8c`
- `0x180002468`
- `0x180006680`
- `0x18001a3a0`
- `0x180030ab8`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001a4f8`
- `KERNEL32!HeapFree` at `0x18001a5c7`
- `KERNEL32!HeapFree` at `0x18001a631`
- `KERNEL32!HeapFree` at `0x18001a4f8`
- `KERNEL32!HeapFree` at `0x18001a5c7`
- `KERNEL32!HeapFree` at `0x18001a631`
- `KERNEL32!GetProcessHeap` at `0x18001a4e3`
- `KERNEL32!GetProcessHeap` at `0x18001a5b2`
- `KERNEL32!GetProcessHeap` at `0x18001a61c`
- `KERNEL32!GetProcessHeap` at `0x18001a4e3`
- `KERNEL32!GetProcessHeap` at `0x18001a5b2`
- `KERNEL32!GetProcessHeap` at `0x18001a61c`

## string_xrefs

- `0x18001a48a`: `.NET Runtime Optimization Service `

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall NGENService::GenerateServiceName(NGENService *this, struct SString *a2)
{
  char v2; // r15
  unsigned int v4; // r12d
  char v5; // r14
  int v6; // eax
  int v7; // ecx
  void *v8; // rsi
  HANDLE ProcessHeap; // rax
  int v10; // eax
  int v11; // ecx
  void *v12; // rsi
  HANDLE v13; // rax
  unsigned __int16 *v14; // rdx
  bool v15; // r8
  void *v16; // rdi
  HANDLE v17; // rax
  _QWORD *v19; // rbx
  BOOL v20; // esi
  _QWORD *v21; // rcx
  _QWORD *v22; // rcx
  IErrorInfo *v23; // rax
  IErrorInfo *v24; // rdi
  int v25; // [rsp+20h] [rbp-6D8h] BYREF
  _QWORD *v26; // [rsp+28h] [rbp-6D0h]
  int *v27; // [rsp+30h] [rbp-6C8h]
  _QWORD v28[4]; // [rsp+38h] [rbp-6C0h] BYREF
  BOOL v29; // [rsp+58h] [rbp-6A0h]
  _QWORD *v30; // [rsp+60h] [rbp-698h] BYREF
  _DWORD v31[2]; // [rsp+70h] [rbp-688h] BYREF
  int v32; // [rsp+78h] [rbp-680h]
  LPVOID lpMem; // [rsp+80h] [rbp-678h]
  __int16 v34; // [rsp+88h] [rbp-670h] BYREF
  _DWORD v35[2]; // [rsp+290h] [rbp-468h] BYREF
  int v36; // [rsp+298h] [rbp-460h]
  LPVOID v37; // [rsp+2A0h] [rbp-458h]
  __int16 v38; // [rsp+2A8h] [rbp-450h] BYREF
  _DWORD v39[2]; // [rsp+4B0h] [rbp-248h] BYREF
  int v40; // [rsp+4B8h] [rbp-240h]
  LPVOID v41; // [rsp+4C0h] [rbp-238h]
  __int16 v42; // [rsp+4C8h] [rbp-230h] BYREF

  v2 = (char)a2;
  v4 = 0;
  v5 = 0;
  v25 = 0;
  v26 = 0;
  try
  {
    try
    {
      v27 = &v25;
      v40 = 0;
      v41 = &v42;
      v39[1] = 512;
      v39[0] = 2;
      v42 = 0;
      Helpers::GetVersionDirectoryFromCurrentModulePath((struct SString *)v39);
      if ( v2 )
      {
        v32 = 0;
        lpMem = &v34;
        v31[1] = 512;
        v31[0] = 2;
        v34 = 0;
        SString::Set((SString *)v31, L".NET Runtime Optimization Service ");
        SBuffer::Set(this, (const struct SBuffer *)v31);
        v6 = v32 & 7;
        *((_DWORD *)this + 2) &= 0xFFFFFFF8;
        v7 = v6 | *((_DWORD *)this + 2);
        *((_DWORD *)this + 2) = v7;
        *((_DWORD *)this + 2) = v7 & 0xFFFFFEFF;
        if ( (v32 & 8) != 0 )
        {
          v8 = lpMem;
          if ( lpMem )
          {
            ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
            if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
            {
              ProcessHeap = GetProcessHeap();
              `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
            }
            HeapFree(ProcessHeap, 0, v8);
          }
        }
      }
      else
      {
        v36 = 0;
        v37 = &v38;
        v35[1] = 512;
        v35[0] = 2;
        v38 = 0;
        SString::Set((SString *)v35, L"clr_optimization_");
        SBuffer::Set(this, (const struct SBuffer *)v35);
        v10 = v36 & 7;
        *((_DWORD *)this + 2) &= 0xFFFFFFF8;
        v11 = v10 | *((_DWORD *)this + 2);
        *((_DWORD *)this + 2) = v11;
        *((_DWORD *)this + 2) = v11 & 0xFFFFFEFF;
        if ( (v36 & 8) != 0 )
        {
          v12 = v37;
          if ( v37 )
          {
            v13 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
            if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
            {
              v13 = GetProcessHeap();
              `ClrFreeInProcessHeap'::`2'::ProcessHeap = v13;
            }
            HeapFree(v13, 0, v12);
          }
        }
      }
      SString::Append(this, (const struct SString *)v39);
      v14 = L" (64 bits)";
      if ( !v2 )
        v14 = L"_64";
      SString::Append(this, v14);
      if ( (v40 & 8) != 0 )
      {
        v16 = v41;
        if ( v41 )
        {
          v17 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
          if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
          {
            v17 = GetProcessHeap();
            `ClrFreeInProcessHeap'::`2'::ProcessHeap = v17;
          }
          HeapFree(v17, 0, v16);
        }
      }
    }
    catch ( Exception *v30 )
    {
      Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v25);
      v26 = v30;
      throw;
    }
  }
  catch ( ... )
  {
    v28[1] = 0;
    v28[0] = &DelegatingException::`vftable';
    v28[2] = -1;
    v19 = v26;
    v28[3] = v26;
    v20 = v26 != 0;
    v29 = v20;
    Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v25, 157, v15);
    v21 = v28;
    if ( v19 )
      v21 = v19;
    LODWORD(v27) = (*(__int64 (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
    v22 = v28;
    if ( v19 )
      v22 = v19;
    v23 = (IErrorInfo *)(*(__int64 (__fastcall **)(_QWORD *))(*v22 + 32LL))(v22);
    v24 = v23;
    if ( v23 )
    {
      SetErrorInfo(0, v23);
      ((void (__fastcall *)(IErrorInfo *))v24->lpVtbl->Release)(v24);
    }
    if ( v20 )
    {
      if ( v19 )
      {
        if ( !(*(unsigned int (__fastcall **)(_QWORD *))(*v19 + 80LL))(v19) )
          (*(void (__fastcall **)(_QWORD *, __int64))*v19)(v19, 5);
      }
      v29 = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)v28);
    v4 = (unsigned int)v27;
    v5 = v25;
  }
  if ( (v5 & 2) != 0 && g_fpHandleStackOverflowAfterCatch )
    g_fpHandleStackOverflowAfterCatch();
  return v4;
}

```

## disassembly

```asm
0x18001a3a0  mov     r11, rsp
0x18001a3a3  mov     [r11+10h], rbx
0x18001a3a7  mov     [r11+18h], rsi
0x18001a3ab  mov     [r11+20h], rdi
0x18001a3af  push    r12
0x18001a3b1  push    r14
0x18001a3b3  push    r15
0x18001a3b5  sub     rsp, 6E0h
0x18001a3bc  mov     rax, cs:__security_cookie
0x18001a3c3  xor     rax, rsp
0x18001a3c6  mov     [rsp+6F8h+var_28], rax
0x18001a3ce  mov     r15b, dl
0x18001a3d1  mov     rdi, rcx
0x18001a3d4  xor     ebx, ebx
0x18001a3d6  mov     r12d, ebx
0x18001a3d9  mov     r14d, ebx
0x18001a3dc  mov     [rsp+6F8h+var_6D8], ebx
0x18001a3e0  mov     [rsp+6F8h+var_6D0], rbx
0x18001a3e5  lea     rax, [rsp+6F8h+var_6D8]
0x18001a3ea  mov     [rsp+6F8h+var_6C8], rax
0x18001a3ef  mov     [rsp+6F8h+var_248], ebx
0x18001a3f6  mov     [rsp+6F8h+var_244], ebx
0x18001a3fd  mov     [rsp+6F8h+var_240], ebx
0x18001a404  mov     [r11-238h], rbx
0x18001a40b  lea     rax, [r11-230h]
0x18001a412  mov     [r11-238h], rax
0x18001a419  mov     esi, 200h
0x18001a41e  mov     [rsp+6F8h+var_244], esi
0x18001a425  mov     [rsp+6F8h+var_248], 2
0x18001a430  mov     rax, [r11-238h]
0x18001a437  mov     [rax], bx
0x18001a43a  lea     rcx, [r11-248h]; this
0x18001a441  call    ?GetVersionDirectoryFromCurrentModulePath@Helpers@@SAXAEAVSString@@@Z; Helpers::GetVersionDirectoryFromCurrentModulePath(SString &)
0x18001a446  test    r15b, r15b
0x18001a449  jz      loc_18001A503
0x18001a44f  mov     [rsp+6F8h+var_688], ebx
0x18001a453  mov     [rsp+6F8h+var_684], ebx
0x18001a457  mov     [rsp+6F8h+var_680], ebx
0x18001a45b  mov     [rsp+6F8h+lpMem], rbx
0x18001a463  lea     rax, [rsp+6F8h+var_670]
0x18001a46b  mov     [rsp+6F8h+lpMem], rax
0x18001a473  mov     [rsp+6F8h+var_684], esi
0x18001a477  mov     [rsp+6F8h+var_688], 2
0x18001a47f  mov     rax, [rsp+6F8h+lpMem]
0x18001a487  mov     [rax], bx
0x18001a48a  lea     rdx, aNetRuntimeOpti; ".NET Runtime Optimization Service "
0x18001a491  lea     rcx, [rsp+6F8h+var_688]; this
0x18001a496  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18001a49b  nop
0x18001a49c  lea     rdx, [rsp+6F8h+var_688]; struct SBuffer *
0x18001a4a1  mov     rcx, rdi; this
0x18001a4a4  call    ?Set@SBuffer@@QEAAXAEBV1@@Z; SBuffer::Set(SBuffer const &)
0x18001a4a9  mov     eax, [rsp+6F8h+var_680]
0x18001a4ad  and     eax, 7
0x18001a4b0  and     dword ptr [rdi+8], 0FFFFFFF8h
0x18001a4b4  mov     ecx, [rdi+8]
0x18001a4b7  or      ecx, eax
0x18001a4b9  mov     [rdi+8], ecx
0x18001a4bc  btr     ecx, 8
0x18001a4c0  mov     [rdi+8], ecx
0x18001a4c3  test    byte ptr [rsp+6F8h+var_680], 8
0x18001a4c8  jz      short loc_18001A4FE
0x18001a4ca  mov     rsi, [rsp+6F8h+lpMem]
0x18001a4d2  test    rsi, rsi
0x18001a4d5  jz      short loc_18001A4FE
0x18001a4d7  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001a4de  test    rax, rax
0x18001a4e1  jnz     short loc_18001A4F0
0x18001a4e3  call    cs:__imp_GetProcessHeap
0x18001a4e9  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001a4f0  mov     r8, rsi; lpMem
0x18001a4f3  xor     edx, edx; dwFlags
0x18001a4f5  mov     rcx, rax; hHeap
0x18001a4f8  call    cs:__imp_HeapFree
0x18001a4fe  jmp     loc_18001A5CD
0x18001a503  mov     [rsp+6F8h+var_468], ebx
0x18001a50a  mov     [rsp+6F8h+var_464], ebx
0x18001a511  mov     [rsp+6F8h+var_460], ebx
0x18001a518  mov     [rsp+6F8h+var_458], rbx
0x18001a520  lea     rax, [rsp+6F8h+var_450]
0x18001a528  mov     [rsp+6F8h+var_458], rax
0x18001a530  mov     [rsp+6F8h+var_464], esi
0x18001a537  mov     [rsp+6F8h+var_468], 2
0x18001a542  mov     rax, [rsp+6F8h+var_458]
0x18001a54a  mov     [rax], bx
0x18001a54d  lea     rdx, aClrOptimizatio; "clr_optimization_"
0x18001a554  lea     rcx, [rsp+6F8h+var_468]; this
0x18001a55c  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18001a561  nop
0x18001a562  lea     rdx, [rsp+6F8h+var_468]; struct SBuffer *
0x18001a56a  mov     rcx, rdi; this
0x18001a56d  call    ?Set@SBuffer@@QEAAXAEBV1@@Z; SBuffer::Set(SBuffer const &)
0x18001a572  mov     eax, [rsp+6F8h+var_460]
0x18001a579  and     eax, 7
0x18001a57c  and     dword ptr [rdi+8], 0FFFFFFF8h
0x18001a580  mov     ecx, [rdi+8]
0x18001a583  or      ecx, eax
0x18001a585  mov     [rdi+8], ecx
0x18001a588  btr     ecx, 8
0x18001a58c  mov     [rdi+8], ecx
0x18001a58f  test    byte ptr [rsp+6F8h+var_460], 8
0x18001a597  jz      short loc_18001A5CD
0x18001a599  mov     rsi, [rsp+6F8h+var_458]
0x18001a5a1  test    rsi, rsi
0x18001a5a4  jz      short loc_18001A5CD
0x18001a5a6  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001a5ad  test    rax, rax
0x18001a5b0  jnz     short loc_18001A5BF
0x18001a5b2  call    cs:__imp_GetProcessHeap
0x18001a5b8  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001a5bf  mov     r8, rsi; lpMem
0x18001a5c2  xor     edx, edx; dwFlags
0x18001a5c4  mov     rcx, rax; hHeap
0x18001a5c7  call    cs:__imp_HeapFree
0x18001a5cd  lea     rdx, [rsp+6F8h+var_248]; struct SString *
0x18001a5d5  mov     rcx, rdi; this
0x18001a5d8  call    ?Append@SString@@QEAAXAEBV1@@Z; SString::Append(SString const &)
0x18001a5dd  mov     rcx, rdi; this
0x18001a5e0  test    r15b, r15b
0x18001a5e3  lea     rdx, a64Bits; " (64 bits)"
0x18001a5ea  jnz     short loc_18001A5F3
0x18001a5ec  lea     rdx, a64; "_64"
0x18001a5f3  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18001a5f8  nop
0x18001a5f9  test    byte ptr [rsp+6F8h+var_240], 8
0x18001a601  jz      short loc_18001A638
0x18001a603  mov     rdi, [rsp+6F8h+var_238]
0x18001a60b  test    rdi, rdi
0x18001a60e  jz      short loc_18001A638
0x18001a610  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001a617  test    rax, rax
0x18001a61a  jnz     short loc_18001A629
0x18001a61c  call    cs:__imp_GetProcessHeap
0x18001a622  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001a629  mov     r8, rdi; lpMem
0x18001a62c  xor     edx, edx; dwFlags
0x18001a62e  mov     rcx, rax; hHeap
0x18001a631  call    cs:__imp_HeapFree
0x18001a637  nop
0x18001a638  jmp     short loc_18001A644
0x18001a63a  mov     r12d, dword ptr [rsp+6F8h+var_6C8]
0x18001a63f  mov     r14d, [rsp+6F8h+var_6D8]
0x18001a644  test    r14b, 2
0x18001a648  jz      short loc_18001A65C
0x18001a64a  mov     rax, cs:?g_fpHandleStackOverflowAfterCatch@@3P6AXXZEA; void (*g_fpHandleStackOverflowAfterCatch)(void)
0x18001a651  test    rax, rax
0x18001a654  jz      short loc_18001A65C
0x18001a656  call    cs:__guard_dispatch_icall_fptr
0x18001a65c  mov     eax, r12d
0x18001a65f  mov     rcx, [rsp+6F8h+var_28]
0x18001a667  xor     rcx, rsp; StackCookie
0x18001a66a  call    __security_check_cookie
0x18001a66f  lea     r11, [rsp+6F8h+var_18]
0x18001a677  mov     rbx, [r11+28h]
0x18001a67b  mov     rsi, [r11+30h]
0x18001a67f  mov     rdi, [r11+38h]
0x18001a683  mov     rsp, r11
0x18001a686  pop     r15
0x18001a688  pop     r14
0x18001a68a  pop     r12
0x18001a68c  retn
```
