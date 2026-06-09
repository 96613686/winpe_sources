# UtilLoadResourceString(CCompRC::ResourceCategory,uint,ushort *,int)

- ea: `0x1800399b0`
- end: `0x180039a6d`
- name: `?UtilLoadResourceString@@YAJW4ResourceCategory@CCompRC@@IPEAGH@Z`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180039890`
- `0x18003e794`

## callees

- `0x180006840`
- `0x18003007c`
- `0x1800300c0`
- `0x180030384`
- `0x1800399b0`
- `0x18003efb0`
- `0x18003f898`
- `0x18003fd88`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilLoadResourceString(unsigned int a1, unsigned int a2, __int64 a3, int a4)
{
  unsigned int v8; // edx
  unsigned int String; // edi
  struct CCompRC *DefaultResourceDll; // rax
  __int64 v12; // [rsp+30h] [rbp-78h]
  int v13; // [rsp+38h] [rbp-70h]
  __int64 v14; // [rsp+40h] [rbp-68h] BYREF
  _DWORD v15[4]; // [rsp+48h] [rbp-60h] BYREF
  __int64 v16; // [rsp+58h] [rbp-50h] BYREF
  BOOL v17; // [rsp+60h] [rbp-48h]
  _QWORD v18[8]; // [rsp+68h] [rbp-40h] BYREF

  SOIntolerantTransitionHandler::SOIntolerantTransitionHandler((SOIntolerantTransitionHandler *)v15);
  if ( (unsigned int)SOIntolerantTransitionHandler::RetailStackProbeNoThrowNoThread(
                       (SOIntolerantTransitionHandler *)v15,
                       v8) )
  {
    String = -2147024882;
    SString::Startup();
    v12 = 0;
    try
    {
      try
      {
        DefaultResourceDll = CCompRC::GetDefaultResourceDll();
        if ( DefaultResourceDll )
          String = CCompRC::LoadString(DefaultResourceDll, a1, a2, a3, a4, 0, 0);
      }
      catch ( Exception *v14 )
      {
        throw;
      }
    }
    catch ( ... )
    {
      v13 = IsCurrentExceptionSO();
      v16 = v12;
      v17 = v12 != 0;
      v18[1] = 0;
      v18[0] = &DelegatingException::`vftable';
      v18[2] = -1;
      DelegatingException::~DelegatingException((DelegatingException *)v18);
      Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2>::~Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2>(&v16);
      if ( v13 )
        HandleStackOverflowAfterCatch();
      String = -2147024882;
    }
    v15[0] = 0;
    SOIntolerantTransitionHandler::~SOIntolerantTransitionHandler((SOIntolerantTransitionHandler *)v15);
    return String;
  }
  else
  {
    v15[0] = 0;
    SOIntolerantTransitionHandler::~SOIntolerantTransitionHandler((SOIntolerantTransitionHandler *)v15);
    return 2147943401LL;
  }
}

```

## disassembly

```asm
0x1800399b0  push    rsi
0x1800399b2  push    rdi
0x1800399b3  push    r12
0x1800399b5  push    r14
0x1800399b7  push    r15
0x1800399b9  sub     rsp, 80h
0x1800399c0  mov     esi, r9d
0x1800399c3  mov     r14, r8
0x1800399c6  mov     r15d, edx
0x1800399c9  mov     r12d, ecx
0x1800399cc  lea     rcx, [rsp+0A8h+var_60]; this
0x1800399d1  call    ??0SOIntolerantTransitionHandler@@QEAA@XZ; SOIntolerantTransitionHandler::SOIntolerantTransitionHandler(void)
0x1800399d6  nop
0x1800399d7  lea     rcx, [rsp+0A8h+var_60]; this
0x1800399dc  call    ?RetailStackProbeNoThrowNoThread@SOIntolerantTransitionHandler@@QEAAHI@Z; SOIntolerantTransitionHandler::RetailStackProbeNoThrowNoThread(uint)
0x1800399e1  test    eax, eax
0x1800399e3  jnz     short loc_1800399FA
0x1800399e5  mov     [rsp+0A8h+var_60], eax
0x1800399e9  lea     rcx, [rsp+0A8h+var_60]; this
0x1800399ee  call    ??1SOIntolerantTransitionHandler@@QEAA@XZ; SOIntolerantTransitionHandler::~SOIntolerantTransitionHandler(void)
0x1800399f3  mov     eax, 800703E9h
0x1800399f8  jmp     short loc_180039A5D
0x1800399fa  mov     edi, 8007000Eh
0x1800399ff  call    ?Startup@SString@@SAXXZ; SString::Startup(void)
0x180039a04  mov     [rsp+0A8h+var_78], 0
0x180039a0d  call    ?GetDefaultResourceDll@CCompRC@@SAPEAV1@XZ; CCompRC::GetDefaultResourceDll(void)
0x180039a12  test    rax, rax
0x180039a15  jz      short loc_180039A37
0x180039a17  mov     [rsp+0A8h+var_80], 0
0x180039a20  mov     [rsp+0A8h+var_88], esi
0x180039a24  mov     r9, r14
0x180039a27  mov     r8d, r15d
0x180039a2a  mov     edx, r12d
0x180039a2d  mov     rcx, rax
0x180039a30  call    ?LoadString@CCompRC@@QEAAJW4ResourceCategory@1@IPEAGHPEAH@Z; CCompRC::LoadString(CCompRC::ResourceCategory,uint,ushort *,int,int *)
0x180039a35  mov     edi, eax
0x180039a37  jmp     short loc_180039A49
0x180039a39  cmp     [rsp+0A8h+var_70], 0
0x180039a3e  jz      short loc_180039A45
0x180039a40  call    ?HandleStackOverflowAfterCatch@@YAXXZ; HandleStackOverflowAfterCatch(void)
0x180039a45  mov     edi, dword ptr [rsp+0A8h+var_78]
0x180039a49  mov     [rsp+0A8h+var_60], 0
0x180039a51  lea     rcx, [rsp+0A8h+var_60]; this
0x180039a56  call    ??1SOIntolerantTransitionHandler@@QEAA@XZ; SOIntolerantTransitionHandler::~SOIntolerantTransitionHandler(void)
0x180039a5b  mov     eax, edi
0x180039a5d  add     rsp, 80h
0x180039a64  pop     r15
0x180039a66  pop     r14
0x180039a68  pop     r12
0x180039a6a  pop     rdi
0x180039a6b  pop     rsi
0x180039a6c  retn
```
