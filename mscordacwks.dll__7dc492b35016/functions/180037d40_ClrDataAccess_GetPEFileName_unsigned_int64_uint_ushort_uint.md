# ClrDataAccess::GetPEFileName(unsigned __int64,uint,ushort *,uint *)

- ea: `0x180037d40`
- end: `0x1800380b6`
- name: `?GetPEFileName@ClrDataAccess@@UEAAJ_KIPEAGPEAI@Z`
- size: `886`
- prototype: `int(ClrDataAccess *__hidden this, unsigned __int64, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x18000b8c0`
- `0x180020f50`
- `0x1800210f0`
- `0x18002127c`
- `0x180022068`
- `0x180037d40`
- `0x180040974`
- `0x18007344c`
- `0x180074898`
- `0x1800f0d20`
- `0x1800f5978`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180037da2`
- `KERNEL32!EnterCriticalSection` at `0x180037da2`
- `KERNEL32!LeaveCriticalSection` at `0x180038084`
- `KERNEL32!LeaveCriticalSection` at `0x180038084`
- `KERNEL32!HeapFree` at `0x18003804d`
- `KERNEL32!HeapFree` at `0x18003804d`
- `KERNEL32!GetProcessHeap` at `0x180038038`
- `KERNEL32!GetProcessHeap` at `0x180038038`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ClrDataAccess::GetPEFileName(
        ClrDataAccess *this,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int *a5)
{
  rsize_t v6; // r12
  unsigned int v9; // ebx
  ClrDataAccess *v11; // r13
  __int64 v12; // rdx
  __int64 *v13; // rdi
  __int64 v14; // r8
  unsigned __int64 v15; // rcx
  unsigned __int64 *v16; // rax
  _BYTE *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned __int64 v20; // rcx
  unsigned __int64 *v21; // rax
  SString *v22; // rax
  __int64 *v23; // rcx
  int v24; // r8d
  __int64 *v25; // rax
  unsigned int v26; // edi
  wchar_t *v27; // rdi
  HANDLE ProcessHeap; // rax
  struct Exception *v30; // rbx
  BOOL v31; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v33; // rcx
  unsigned int v34; // [rsp+20h] [rbp-2C8h] BYREF
  __int64 TargetAddrForHostAddr; // [rsp+28h] [rbp-2C0h]
  BOOL v36; // [rsp+30h] [rbp-2B8h]
  unsigned int v37; // [rsp+38h] [rbp-2B0h]
  ClrDataAccess *v38; // [rsp+40h] [rbp-2A8h]
  unsigned __int64 v39; // [rsp+50h] [rbp-298h]
  _QWORD v40[3]; // [rsp+58h] [rbp-290h] BYREF
  unsigned __int64 v41; // [rsp+70h] [rbp-278h] BYREF
  _DWORD v42[2]; // [rsp+80h] [rbp-268h] BYREF
  int v43; // [rsp+88h] [rbp-260h]
  wchar_t *Source; // [rsp+90h] [rbp-258h]
  __int16 v45; // [rsp+98h] [rbp-250h] BYREF

  v6 = a3;
  v9 = 0;
  if ( !a2 )
    return 2147942487LL;
  if ( a4 ? a3 == 0 : a5 == 0 )
    return 2147942487LL;
  EnterCriticalSection(&g_dacCritSec);
  v11 = g_dacImpl;
  v38 = g_dacImpl;
  g_dacImpl = (ClrDataAccess *)((char *)this - 16);
  v34 = 0;
  v39 = 0;
  try
  {
    try
    {
      TargetAddrForHostAddr = a2;
      v13 = DacInstantiateClassByVTable(a2, 200, 1);
      v15 = v13[1];
      if ( v15 )
      {
        v17 = DacInstantiateTypeByAddressHelper(v15, 0xD0u, 1, 1);
      }
      else
      {
        TargetAddrForHostAddr = (unsigned int)*SString::s_Empty[0] + DacGlobalBase(0, v12, v14);
        v16 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(TargetAddrForHostAddr, 8u, 1, 1);
        v17 = DacInstantiateTypeByAddressHelper(*v16, 0x18u, 1, 1);
      }
      if ( *(_DWORD *)v17 >> ((v17[8] & 1) == 0) == 1 )
      {
        if ( v13[1] )
        {
          LOBYTE(v18) = 1;
          if ( (v13[14] & 2) != 0 )
          {
            TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(v13, v18);
            v23 = DacInstantiateClassByVTable(TargetAddrForHostAddr, 280, 1);
          }
          else
          {
            TargetAddrForHostAddr = DacGetTargetAddrForHostAddr(v13, v18);
            v25 = DacInstantiateClassByVTable(TargetAddrForHostAddr, 216, 1);
            v23 = DacInstantiateClassByVTable(v25[25], 280, 1);
          }
          v43 = 0;
          Source = (wchar_t *)&v45;
          v42[1] = 512;
          v42[0] = 2;
          v45 = 0;
          PEAssembly::GetDisplayName((PEAssembly *)v23, (struct SString *)v42, v24);
          if ( v42[0] >> ((v43 & 1) == 0) == 1 )
          {
            if ( a4 )
              *a4 = 0;
            if ( a5 )
              *a5 = 1;
          }
          else
          {
            v26 = SString::GetCount((SString *)v42) + 1;
            v37 = v26;
            if ( a4 )
            {
              SString::ConvertToUnicode((SString *)v42);
              wcsncpy_s(a4, v6, Source, 0xFFFFFFFFFFFFFFFFuLL);
              if ( (unsigned int)v6 < v26 )
                v26 = v6;
              v37 = v26;
            }
            if ( a5 )
              *a5 = v26;
          }
          if ( (v43 & 8) != 0 )
          {
            v27 = Source;
            if ( Source )
            {
              ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
              if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
              {
                ProcessHeap = GetProcessHeap();
                `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
              }
              HeapFree(ProcessHeap, 0, v27);
            }
          }
        }
        else
        {
          if ( a4 && (_DWORD)v6 )
            *a4 = 0;
          if ( a5 )
            *a5 = 1;
        }
      }
      else
      {
        v20 = v13[1];
        if ( v20 )
        {
          v22 = (SString *)DacInstantiateTypeByAddressHelper(v20, 0xD0u, 1, 1);
        }
        else
        {
          TargetAddrForHostAddr = (unsigned int)*SString::s_Empty[0] + DacGlobalBase(0, v18, v19);
          v21 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(TargetAddrForHostAddr, 8u, 1, 1);
          v22 = (SString *)DacInstantiateTypeByAddressHelper(*v21, 0x18u, 1, 1);
        }
        if ( !SString::DacGetUnicode(v22, v6, a4, a5) )
        {
          v9 = -2147467259;
          v34 = -2147467259;
        }
      }
    }
    catch ( Exception *v41 )
    {
      v39 = v41;
      throw;
    }
  }
  catch ( ... )
  {
    v40[1] = 0;
    v40[0] = &DelegatingException::`vftable';
    v40[2] = -1;
    v30 = (struct Exception *)v39;
    TargetAddrForHostAddr = v39;
    v31 = v39 != 0;
    v36 = v31;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v33 = (struct Exception *)v40;
    if ( v30 )
      v33 = v30;
    if ( !DacExceptionFilter(v33, (ClrDataAccess *)((char *)this - 16), (int *)&v34) )
    {
      v36 = 0;
      throw;
    }
    if ( v31 )
    {
      if ( v30 )
      {
        if ( !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v30 + 80LL))(v30) )
          (**(void (__fastcall ***)(struct Exception *, __int64))v30)(v30, 5);
      }
      v36 = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)v40);
    v11 = v38;
    v9 = v34;
  }
  g_dacImpl = v11;
  LeaveCriticalSection(&g_dacCritSec);
  return v9;
}

```

## disassembly

```asm
0x180037d40  mov     [rsp+arg_0], rcx
0x180037d45  push    rbx
0x180037d46  push    rsi
0x180037d47  push    rdi
0x180037d48  push    r12
0x180037d4a  push    r13
0x180037d4c  push    r14
0x180037d4e  push    r15
0x180037d50  sub     rsp, 2B0h
0x180037d57  mov     rax, cs:__security_cookie
0x180037d5e  xor     rax, rsp
0x180037d61  mov     [rsp+2E8h+var_48], rax
0x180037d69  mov     r15, r9
0x180037d6c  mov     r12d, r8d
0x180037d6f  mov     rdi, rdx
0x180037d72  mov     rsi, rcx
0x180037d75  mov     r14, [rsp+2E8h+arg_20]
0x180037d7d  xor     ebx, ebx
0x180037d7f  test    rdx, rdx
0x180037d82  jz      loc_18003808E
0x180037d88  test    r9, r9
0x180037d8b  jnz     short loc_180037D92
0x180037d8d  test    r14, r14
0x180037d90  jmp     short loc_180037D95
0x180037d92  test    r8d, r8d
0x180037d95  jz      loc_18003808E
0x180037d9b  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180037da2  call    cs:__imp_EnterCriticalSection
0x180037da8  mov     r13, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x180037daf  mov     [rsp+2E8h+var_2A8], r13
0x180037db4  lea     rax, [rsi-10h]
0x180037db8  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x180037dbf  mov     [rsp+2E8h+var_2C8], ebx
0x180037dc3  mov     [rsp+2E8h+var_298], rbx
0x180037dc8  lea     rax, [rsp+2E8h+var_2A0]
0x180037dcd  mov     [rsp+2E8h+var_2C0], rax
0x180037dd2  mov     [rsp+2E8h+var_2C0], rdi
0x180037dd7  mov     esi, 1
0x180037ddc  mov     r8b, sil
0x180037ddf  mov     edx, 0C8h
0x180037de4  mov     rcx, rdi; unsigned __int64
0x180037de7  call    DacInstantiateClassByVTable
0x180037dec  mov     rdi, rax
0x180037def  mov     rcx, [rax+8]; unsigned __int64
0x180037df3  test    rcx, rcx
0x180037df6  jnz     short loc_180037E35
0x180037df8  call    DacGlobalBase
0x180037dfd  mov     r10, rax
0x180037e00  mov     rax, cs:?s_Empty@SString@@0V?$__GlobalPtr@PEAVSString@@V?$__DPtr@VSString@@@@@@A; __GlobalPtr<SString *,__DPtr<SString>> SString::s_Empty
0x180037e07  mov     ecx, [rax]
0x180037e09  add     r10, rcx
0x180037e0c  mov     [rsp+2E8h+var_2C0], r10
0x180037e11  mov     r9b, sil; bool
0x180037e14  mov     r8b, sil; bool
0x180037e17  lea     edx, [rsi+7]; unsigned int
0x180037e1a  mov     rcx, r10; unsigned __int64
0x180037e1d  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180037e22  mov     r9b, sil; bool
0x180037e25  mov     r8b, sil; bool
0x180037e28  lea     edx, [rsi+17h]; unsigned int
0x180037e2b  mov     rcx, [rax]; unsigned __int64
0x180037e2e  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180037e33  jmp     short loc_180037E45
0x180037e35  mov     r9b, sil; bool
0x180037e38  mov     r8b, sil; bool
0x180037e3b  mov     edx, 0D0h; unsigned int
0x180037e40  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180037e45  mov     ecx, [rax+8]
0x180037e48  not     ecx
0x180037e4a  and     ecx, esi
0x180037e4c  mov     eax, [rax]
0x180037e4e  shr     eax, cl
0x180037e50  cmp     eax, esi
0x180037e52  jz      short loc_180037ED3
0x180037e54  mov     rcx, [rdi+8]; unsigned __int64
0x180037e58  test    rcx, rcx
0x180037e5b  jnz     short loc_180037E9C
0x180037e5d  call    DacGlobalBase
0x180037e62  mov     rcx, rax
0x180037e65  mov     rax, cs:?s_Empty@SString@@0V?$__GlobalPtr@PEAVSString@@V?$__DPtr@VSString@@@@@@A; __GlobalPtr<SString *,__DPtr<SString>> SString::s_Empty
0x180037e6c  mov     r8d, [rax]
0x180037e6f  add     rcx, r8; unsigned __int64
0x180037e72  mov     [rsp+2E8h+var_2C0], rcx
0x180037e77  mov     r9b, sil; bool
0x180037e7a  mov     r8b, sil; bool
0x180037e7d  mov     edx, 8; unsigned int
0x180037e82  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180037e87  mov     r9b, sil; bool
0x180037e8a  mov     r8b, sil; bool
0x180037e8d  mov     edx, 18h; unsigned int
0x180037e92  mov     rcx, [rax]; unsigned __int64
0x180037e95  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180037e9a  jmp     short loc_180037EAC
0x180037e9c  mov     r9b, sil; bool
0x180037e9f  mov     r8b, sil; bool
0x180037ea2  mov     edx, 0D0h; unsigned int
0x180037ea7  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180037eac  mov     r9, r14; unsigned int *
0x180037eaf  mov     r8, r15; unsigned __int16 *
0x180037eb2  mov     edx, r12d; cchWideChar
0x180037eb5  mov     rcx, rax; this
0x180037eb8  call    ?DacGetUnicode@SString@@QEBA_NIPEAGPEAI@Z; SString::DacGetUnicode(uint,ushort *,uint *)
0x180037ebd  test    al, al
0x180037ebf  jnz     loc_18003806B
0x180037ec5  mov     ebx, 80004005h
0x180037eca  mov     [rsp+2E8h+var_2C8], ebx
0x180037ece  jmp     loc_18003806B
0x180037ed3  cmp     [rdi+8], rbx
0x180037ed7  jz      loc_180038055
0x180037edd  test    byte ptr [rdi+70h], 2
0x180037ee1  jz      short loc_180037F08
0x180037ee3  mov     dl, sil
0x180037ee6  mov     rcx, rdi
0x180037ee9  call    DacGetTargetAddrForHostAddr
0x180037eee  mov     [rsp+2E8h+var_2C0], rax
0x180037ef3  mov     r8b, sil
0x180037ef6  mov     edx, 118h
0x180037efb  mov     rcx, rax; unsigned __int64
0x180037efe  call    DacInstantiateClassByVTable
0x180037f03  mov     rcx, rax
0x180037f06  jmp     short loc_180037F3F
0x180037f08  mov     dl, sil
0x180037f0b  mov     rcx, rdi
0x180037f0e  call    DacGetTargetAddrForHostAddr
0x180037f13  mov     [rsp+2E8h+var_2C0], rax
0x180037f18  mov     r8b, sil
0x180037f1b  mov     edx, 0D8h
0x180037f20  mov     rcx, rax; unsigned __int64
0x180037f23  call    DacInstantiateClassByVTable
0x180037f28  mov     r8b, sil
0x180037f2b  mov     edx, 118h
0x180037f30  mov     rcx, [rax+0C8h]; unsigned __int64
0x180037f37  call    DacInstantiateClassByVTable
0x180037f3c  mov     rcx, rax; this
0x180037f3f  mov     [rsp+2E8h+var_268], ebx
0x180037f46  mov     [rsp+2E8h+var_264], ebx
0x180037f4d  mov     [rsp+2E8h+var_260], ebx
0x180037f54  mov     [rsp+2E8h+Source], rbx
0x180037f5c  lea     rax, [rsp+2E8h+var_250]
0x180037f64  mov     [rsp+2E8h+Source], rax
0x180037f6c  mov     [rsp+2E8h+var_264], 200h
0x180037f77  mov     [rsp+2E8h+var_268], 2
0x180037f82  mov     rax, [rsp+2E8h+Source]
0x180037f8a  mov     [rax], bx
0x180037f8d  lea     rdx, [rsp+2E8h+var_268]; struct SString *
0x180037f95  call    ?GetDisplayName@PEAssembly@@QEAAXAEAVSString@@K@Z; PEAssembly::GetDisplayName(SString &,ulong)
0x180037f9a  mov     ecx, [rsp+2E8h+var_260]
0x180037fa1  not     ecx
0x180037fa3  and     ecx, esi
0x180037fa5  mov     eax, [rsp+2E8h+var_268]
0x180037fac  shr     eax, cl
0x180037fae  cmp     eax, esi
0x180037fb0  jnz     short loc_180037FC5
0x180037fb2  test    r15, r15
0x180037fb5  jz      short loc_180037FBB
0x180037fb7  mov     [r15], bx
0x180037fbb  test    r14, r14
0x180037fbe  jz      short loc_180038015
0x180037fc0  mov     [r14], esi
0x180037fc3  jmp     short loc_180038015
0x180037fc5  lea     rcx, [rsp+2E8h+var_268]; this
0x180037fcd  call    ?GetCount@SString@@QEBAIXZ; SString::GetCount(void)
0x180037fd2  lea     edi, [rsi+rax]
0x180037fd5  mov     [rsp+2E8h+var_2B0], edi
0x180037fd9  test    r15, r15
0x180037fdc  jz      short loc_18003800D
0x180037fde  lea     rcx, [rsp+2E8h+var_268]; this
0x180037fe6  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180037feb  mov     rdx, r12; SizeInWords
0x180037fee  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180037ff2  mov     r8, [rsp+2E8h+Source]; Source
0x180037ffa  mov     rcx, r15; Destination
0x180037ffd  call    wcsncpy_s
0x180038002  cmp     r12d, edi
0x180038005  cmovb   edi, r12d
0x180038009  mov     [rsp+2E8h+var_2B0], edi
0x18003800d  test    r14, r14
0x180038010  jz      short loc_180038015
0x180038012  mov     [r14], edi
0x180038015  test    byte ptr [rsp+2E8h+var_260], 8
0x18003801d  jz      short loc_180038053
0x18003801f  mov     rdi, [rsp+2E8h+Source]
0x180038027  test    rdi, rdi
0x18003802a  jz      short loc_180038053
0x18003802c  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180038033  test    rax, rax
0x180038036  jnz     short loc_180038045
0x180038038  call    cs:__imp_GetProcessHeap
0x18003803e  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180038045  mov     r8, rdi; lpMem
0x180038048  xor     edx, edx; dwFlags
0x18003804a  mov     rcx, rax; hHeap
0x18003804d  call    cs:__imp_HeapFree
0x180038053  jmp     short loc_18003806B
0x180038055  test    r15, r15
0x180038058  jz      short loc_180038063
0x18003805a  test    r12d, r12d
0x18003805d  jz      short loc_180038063
0x18003805f  mov     [r15], bx
0x180038063  test    r14, r14
0x180038066  jz      short loc_18003806B
0x180038068  mov     [r14], esi
0x18003806b  jmp     short loc_180038076
0x18003806d  mov     r13, [rsp+2E8h+var_2A8]
0x180038072  mov     ebx, [rsp+2E8h+var_2C8]
0x180038076  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r13; ClrDataAccess * g_dacImpl
0x18003807d  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180038084  call    cs:__imp_LeaveCriticalSection
0x18003808a  mov     eax, ebx
0x18003808c  jmp     short loc_180038093
0x18003808e  mov     eax, 80070057h
0x180038093  mov     rcx, [rsp+2E8h+var_48]
0x18003809b  xor     rcx, rsp; StackCookie
0x18003809e  call    __security_check_cookie
0x1800380a3  add     rsp, 2B0h
0x1800380aa  pop     r15
0x1800380ac  pop     r14
0x1800380ae  pop     r13
0x1800380b0  pop     r12
0x1800380b2  pop     rdi
0x1800380b3  pop     rsi
0x1800380b4  pop     rbx
0x1800380b5  retn
```
