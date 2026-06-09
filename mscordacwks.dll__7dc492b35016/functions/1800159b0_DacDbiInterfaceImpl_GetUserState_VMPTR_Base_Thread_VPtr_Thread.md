# DacDbiInterfaceImpl::GetUserState(VMPTR_Base<Thread,__VPtr<Thread>>)

- ea: `0x1800159b0`
- end: `0x180015bea`
- name: `?GetUserState@DacDbiInterfaceImpl@@UEAA?AW4CorDebugUserState@@V?$VMPTR_Base@VThread@@V?$__VPtr@VThread@@@@@@@Z`
- size: `570`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x1800159b0`
- `0x180020f50`
- `0x1800210f0`
- `0x18002127c`
- `0x1800905e8`
- `0x1800906b0`
- `0x1800918ac`
- `0x1800f0d20`
- `0x180105e80`
- `0x180106100`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180015a01`
- `KERNEL32!EnterCriticalSection` at `0x180015a54`
- `KERNEL32!EnterCriticalSection` at `0x180015a01`
- `KERNEL32!EnterCriticalSection` at `0x180015a54`
- `KERNEL32!LeaveCriticalSection` at `0x180015b8d`
- `KERNEL32!LeaveCriticalSection` at `0x180015bb1`
- `KERNEL32!LeaveCriticalSection` at `0x180015b8d`
- `KERNEL32!LeaveCriticalSection` at `0x180015bb1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DacDbiInterfaceImpl::GetUserState(__int64 a1, unsigned __int64 a2)
{
  ClrDataAccess *v4; // rsi
  ClrDataAccess *v5; // r15
  __int64 v6; // r12
  unsigned int v7; // r14d
  ClrDataAccess *v8; // r13
  BOOL v9; // edi
  __int64 *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 *v15; // rax
  __int64 v17; // [rsp+30h] [rbp-D0h]
  _BYTE v18[544]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+280h] [rbp+180h]
  _BYTE v20[32]; // [rsp+298h] [rbp+198h] BYREF
  __int64 v21; // [rsp+2B8h] [rbp+1B8h]
  unsigned int v22; // [rsp+2C0h] [rbp+1C0h]
  struct _CONTEXT v23; // [rsp+3D0h] [rbp+2D0h] BYREF
  _BYTE v24[3040]; // [rsp+8A0h] [rbp+7A0h] BYREF

  v4 = (ClrDataAccess *)(a1 - 352);
  EnterCriticalSection(&g_dacCritSec);
  v5 = g_dacImpl;
  v6 = g_pAllocator;
  g_dacImpl = v4;
  g_pAllocator = *((_QWORD *)v4 + 45);
  v7 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)a1 + 336LL))(a1, a2);
  EnterCriticalSection(&g_dacCritSec);
  v8 = g_dacImpl;
  v17 = g_pAllocator;
  g_dacImpl = v4;
  g_pAllocator = *((_QWORD *)v4 + 45);
  v9 = 0;
  v10 = DacInstantiateClassByVTable(a2, 1992, 1);
  v14 = DacGlobalBase(v12, v11, v13);
  if ( (*(_BYTE *)DacInstantiateTypeByAddressHelper((unsigned int)*g_fEEShutDown[0] + v14, 4u, 1, 1) & 4) != 0 )
  {
    v9 = 1;
  }
  else
  {
    SetUpRegdisplayForStackWalk((struct Thread *)v10, &v23, (struct REGDISPLAY *)v24);
    StackFrameIterator::StackFrameIterator((StackFrameIterator *)v18);
    StackFrameIterator::Init((StackFrameIterator *)v18, 152);
    if ( v18[516] && v19 && v18[517] )
    {
      v15 = DacInstantiateClassByVTable(*(_QWORD *)(v21 + 8), 8, 1);
      v9 = (*(unsigned __int8 (__fastcall **)(__int64 *, _BYTE *, _QWORD))(*v15 + 32))(v15, v20, v22) != 0;
    }
  }
  g_dacImpl = v8;
  g_pAllocator = v17;
  LeaveCriticalSection(&g_dacCritSec);
  if ( !v9 )
    v7 |= 0x80u;
  g_dacImpl = v5;
  g_pAllocator = v6;
  LeaveCriticalSection(&g_dacCritSec);
  return v7;
}

```

## disassembly

```asm
0x1800159b0  mov     rax, rsp
0x1800159b3  mov     [rax+10h], rbx
0x1800159b7  mov     [rax+18h], rsi
0x1800159bb  mov     [rax+20h], rdi
0x1800159bf  push    rbp
0x1800159c0  push    r12
0x1800159c2  push    r13
0x1800159c4  push    r14
0x1800159c6  push    r15
0x1800159c8  lea     rbp, [rax-13B8h]
0x1800159cf  mov     eax, 1490h
0x1800159d4  call    _alloca_probe
0x1800159d9  sub     rsp, rax
0x1800159dc  mov     rax, cs:__security_cookie
0x1800159e3  xor     rax, rsp
0x1800159e6  mov     [rbp+13B0h+var_30], rax
0x1800159ed  mov     rbx, rdx
0x1800159f0  mov     rdi, rcx
0x1800159f3  lea     rsi, [rcx-160h]
0x1800159fa  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180015a01  call    cs:__imp_EnterCriticalSection
0x180015a07  mov     r15, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x180015a0e  mov     [rsp+14B0h+var_1478], r15
0x180015a13  mov     r12, cs:g_pAllocator
0x180015a1a  mov     [rsp+14B0h+var_1470], r12
0x180015a1f  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rsi; ClrDataAccess * g_dacImpl
0x180015a26  mov     rax, [rsi+168h]
0x180015a2d  mov     cs:g_pAllocator, rax
0x180015a34  mov     rax, [rdi]
0x180015a37  mov     rdx, rbx
0x180015a3a  mov     rcx, rdi
0x180015a3d  mov     rax, [rax+150h]
0x180015a44  call    cs:__guard_dispatch_icall_fptr
0x180015a4a  mov     r14d, eax
0x180015a4d  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180015a54  call    cs:__imp_EnterCriticalSection
0x180015a5a  mov     r13, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x180015a61  mov     [rsp+14B0h+var_1468], r13
0x180015a66  mov     rax, cs:g_pAllocator
0x180015a6d  mov     [rsp+14B0h+var_1480], rax
0x180015a72  mov     [rsp+14B0h+var_1460], rax
0x180015a77  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rsi; ClrDataAccess * g_dacImpl
0x180015a7e  mov     rcx, [rsi+168h]
0x180015a85  mov     cs:g_pAllocator, rcx
0x180015a8c  xor     esi, esi
0x180015a8e  mov     edi, esi
0x180015a90  mov     edx, 7C8h
0x180015a95  lea     r8d, [rsi+1]
0x180015a99  mov     rcx, rbx; unsigned __int64
0x180015a9c  call    DacInstantiateClassByVTable
0x180015aa1  mov     rbx, rax
0x180015aa4  call    DacGlobalBase
0x180015aa9  mov     rdx, cs:?g_fEEShutDown@@3V?$__GlobalVal@K@@A; __GlobalVal<ulong> g_fEEShutDown
0x180015ab0  mov     r8d, [rdx]
0x180015ab3  add     rax, r8
0x180015ab6  lea     ecx, [rsi+1]
0x180015ab9  mov     r9b, cl; bool
0x180015abc  mov     r8b, cl; bool
0x180015abf  lea     edx, [rsi+4]; unsigned int
0x180015ac2  mov     rcx, rax; unsigned __int64
0x180015ac5  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180015aca  test    byte ptr [rax], 4
0x180015acd  jz      short loc_180015AD7
0x180015acf  lea     edi, [rsi+1]
0x180015ad2  jmp     loc_180015B73
0x180015ad7  lea     r8, [rbp+13B0h+var_C10]; struct REGDISPLAY *
0x180015ade  lea     rdx, [rbp+13B0h+var_10E0]; struct _CONTEXT *
0x180015ae5  mov     rcx, rbx; struct Thread *
0x180015ae8  call    ?SetUpRegdisplayForStackWalk@@YAXPEAVThread@@PEAU_CONTEXT@@PEAUREGDISPLAY@@@Z; SetUpRegdisplayForStackWalk(Thread *,_CONTEXT *,REGDISPLAY *)
0x180015aed  lea     rcx, [rsp+14B0h+var_1450]; this
0x180015af2  call    ??0StackFrameIterator@@QEAA@XZ; StackFrameIterator::StackFrameIterator(void)
0x180015af7  mov     [rsp+14B0h+var_1490], 98h
0x180015aff  lea     r9, [rbp+13B0h+var_C10]
0x180015b06  mov     r8, [rbx+10h]
0x180015b0a  mov     rdx, rbx
0x180015b0d  lea     rcx, [rsp+14B0h+var_1450]
0x180015b12  call    ?Init@StackFrameIterator@@QEAAHPEAVThread@@V?$__VPtr@VFrame@@@@PEAUREGDISPLAY@@I@Z; StackFrameIterator::Init(Thread *,__VPtr<Frame>,REGDISPLAY *,uint)
0x180015b17  cmp     [rbp+13B0h+var_124C], sil
0x180015b1e  jz      short loc_180015B73
0x180015b20  cmp     [rbp+13B0h+var_1230], rsi
0x180015b27  jz      short loc_180015B73
0x180015b29  cmp     [rbp+13B0h+var_124B], sil
0x180015b30  jz      short loc_180015B73
0x180015b32  mov     ebx, 1
0x180015b37  mov     r8b, bl
0x180015b3a  lea     edx, [rbx+7]
0x180015b3d  mov     rcx, [rbp+13B0h+var_11F8]
0x180015b44  mov     rcx, [rcx+8]; unsigned __int64
0x180015b48  call    DacInstantiateClassByVTable
0x180015b4d  mov     r9, rax
0x180015b50  mov     rcx, [rax]
0x180015b53  mov     rax, [rcx+20h]
0x180015b57  mov     r8d, [rbp+13B0h+var_11F0]
0x180015b5e  lea     rdx, [rbp+13B0h+var_1218]
0x180015b65  mov     rcx, r9
0x180015b68  call    cs:__guard_dispatch_icall_fptr
0x180015b6e  test    al, al
0x180015b70  cmovnz  edi, ebx
0x180015b73  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r13; ClrDataAccess * g_dacImpl
0x180015b7a  mov     rax, [rsp+14B0h+var_1480]
0x180015b7f  mov     cs:g_pAllocator, rax
0x180015b86  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180015b8d  call    cs:__imp_LeaveCriticalSection
0x180015b93  test    edi, edi
0x180015b95  jnz     short loc_180015B9C
0x180015b97  bts     r14d, 7
0x180015b9c  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r15; ClrDataAccess * g_dacImpl
0x180015ba3  mov     cs:g_pAllocator, r12
0x180015baa  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180015bb1  call    cs:__imp_LeaveCriticalSection
0x180015bb7  mov     eax, r14d
0x180015bba  mov     rcx, [rbp+13B0h+var_30]
0x180015bc1  xor     rcx, rsp; StackCookie
0x180015bc4  call    __security_check_cookie
0x180015bc9  lea     r11, [rsp+14B0h+var_20]
0x180015bd1  mov     rbx, [r11+38h]
0x180015bd5  mov     rsi, [r11+40h]
0x180015bd9  mov     rdi, [r11+48h]
0x180015bdd  mov     rsp, r11
0x180015be0  pop     r15
0x180015be2  pop     r14
0x180015be4  pop     r13
0x180015be6  pop     r12
0x180015be8  pop     rbp
0x180015be9  retn
```
