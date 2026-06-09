# ScriptEngineBase::VarToNativeArray(void *,JsNativeValueType,uchar * *,uint *,uint *)

- ea: `0x18042f270`
- end: `0x18042f4b9`
- name: `?VarToNativeArray@ScriptEngineBase@@UEAAJPEAXW4JsNativeValueType@@PEAPEAEPEAI3@Z`
- size: `585`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180168cf4`
- `0x1801690a4`
- `0x1801698a4`
- `0x180169c54`
- `0x1802378f0`
- `0x180238138`
- `0x180327e70`
- `0x1803f63a4`
- `0x18042c19c`
- `0x18042f270`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18042f451`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18042f451`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18042f3dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18042f3dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ScriptEngineBase::VarToNativeArray(
        ScriptEngineBase *a1,
        unsigned __int64 a2,
        unsigned int a3,
        _QWORD *a4,
        _DWORD *a5,
        _DWORD *a6)
{
  _QWORD *v6; // r15
  _DWORD *v7; // r12
  __int64 result; // rax
  int v10; // r14d
  struct Js::ScriptContext *v11; // rsi
  void *Property; // rax
  __int64 v13; // rbx
  __int64 v14; // rcx
  int v15; // r8d
  LPVOID v16; // rax
  void **v17; // rax
  void *v18; // rdx
  struct Js::RecyclableObject *v19; // rax
  int RuntimeErrorWithScriptEnter; // [rsp+40h] [rbp-B8h]
  int v21; // [rsp+44h] [rbp-B4h]
  void *pv; // [rsp+48h] [rbp-B0h]
  const Js::JavascriptException *v23; // [rsp+58h] [rbp-A0h] BYREF
  _OWORD v24[3]; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v25[104]; // [rsp+90h] [rbp-68h] BYREF
  void *retaddr; // [rsp+F8h] [rbp+0h] BYREF

  v6 = a4;
  *a4 = 0;
  v7 = a5;
  *a5 = 0;
  result = ScriptEngineBase::VerifyOnEntry(a1, 1);
  v10 = result;
  if ( (int)result >= 0 )
  {
    if ( HIWORD(a2) == 1 || a2 >= 0x4000000000000LL || **(int **)(a2 + 8) <= 24 )
    {
      return 2147942487LL;
    }
    else
    {
      v11 = (struct Js::ScriptContext *)*((_QWORD *)a1 + 1);
      pv = 0;
      memset(v24, 0, sizeof(v24));
      try
      {
        Js::EnterScriptObject::EnterScriptObject(
          (Js::EnterScriptObject *)v25,
          v11,
          (struct Js::ScriptEntryExitRecord *)v24,
          retaddr,
          &retaddr,
          0,
          0,
          0);
        Js::ScriptContext::OnScriptStart(v11, 0, 1);
        Js::EnterScriptObject::VerifyEnterScript((Js::EnterScriptObject *)v25);
        Property = Js::JavascriptOperators::OP_GetProperty((void *)a2, 193, v11);
        v13 = Js::JavascriptConversion::ToLength(Property, v11);
        v15 = lambda_6cadc8d183089854dd15570484b09b0b_::operator()(v14, a3);
        if ( v13 >= 0x7FFFFFFF / v15 || v13 < 0 )
        {
          RuntimeErrorWithScriptEnter = -2147024809;
          v21 = v13;
        }
        else
        {
          v21 = v13;
          *a6 = v15;
          v16 = CoTaskMemAlloc((unsigned int)(v15 * v13));
          pv = v16;
          if ( v16 )
          {
            Js::JavascriptOperators::VarToNativeArray(a2, a3, (unsigned int)v13, (unsigned int)*a6, v16, v11);
            RuntimeErrorWithScriptEnter = v10;
          }
          else
          {
            RuntimeErrorWithScriptEnter = -2147024882;
          }
        }
        Js::EnterScriptObject::~EnterScriptObject((Js::EnterScriptObject *)v25);
      }
      catch ( Js::OutOfMemoryException )
      {
        RuntimeErrorWithScriptEnter = -2147024882;
        goto LABEL_13;
      }
      catch ( Js::StackOverflowException )
      {
        RuntimeErrorWithScriptEnter = -2146828260;
        goto LABEL_13;
      }
      catch ( Js::NotImplementedException )
      {
        RuntimeErrorWithScriptEnter = -2147467263;
        goto LABEL_13;
      }
      catch ( Js::ScriptAbortException )
      {
        RuntimeErrorWithScriptEnter = -2147467260;
        goto LABEL_13;
      }
      catch ( Js::AsmJsParseException )
      {
        RuntimeErrorWithScriptEnter = -2146823140;
        goto LABEL_13;
      }
      catch ( const Js::JavascriptException *v23 )
      {
        v17 = (void **)Js::JavascriptException::GetAndClear(v23);
        if ( *v17 )
        {
          if ( Js::JavascriptError::Is(*v17) || Js::JavascriptError::IsRemoteError(v18) )
          {
            v19 = Js::RecyclableObject::FromVar(v18);
            RuntimeErrorWithScriptEnter = Js::JavascriptError::GetRuntimeErrorWithScriptEnter(v19, 0);
          }
          else
          {
            RuntimeErrorWithScriptEnter = -2146823266;
          }
        }
        else
        {
          RuntimeErrorWithScriptEnter = -2147024882;
        }
        v7 = a5;
        v6 = a4;
        LODWORD(v13) = v21;
      }
      catch ( ... )
      {
        Js::Throw::FatalInternalError(-2147467259);
        JUMPOUT(0x1805BC8B2LL);
      }
      if ( RuntimeErrorWithScriptEnter < 0 )
      {
LABEL_13:
        if ( pv )
          CoTaskMemFree(pv);
        *a6 = 0;
      }
      else
      {
        *v6 = pv;
        *v7 = v13;
      }
      return (unsigned int)RuntimeErrorWithScriptEnter;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18042f270  mov     rax, rsp
0x18042f273  mov     [rax+20h], r9
0x18042f277  mov     [rax+18h], r8d
0x18042f27b  mov     [rax+10h], rdx
0x18042f27f  mov     [rax+8], rcx
0x18042f283  push    rbx
0x18042f284  push    rsi
0x18042f285  push    rdi
0x18042f286  push    r12
0x18042f288  push    r14
0x18042f28a  push    r15
0x18042f28c  sub     rsp, 0C8h
0x18042f293  mov     [rsp+0F8h+var_A8], 0FFFFFFFFFFFFFFFEh
0x18042f29c  mov     r15, r9
0x18042f29f  mov     qword ptr [r9], 0
0x18042f2a6  mov     r12, [rsp+0F8h+arg_20]
0x18042f2ae  mov     dword ptr [r12], 0
0x18042f2b6  mov     edx, 1; int
0x18042f2bb  mov     rbx, rcx
0x18042f2be  call    ?VerifyOnEntry@ScriptEngineBase@@QEAAJH@Z; ScriptEngineBase::VerifyOnEntry(int)
0x18042f2c3  mov     r14d, eax
0x18042f2c6  test    eax, eax
0x18042f2c8  js      loc_18042F4A7
0x18042f2ce  mov     rdi, [rsp+0F8h+arg_8]
0x18042f2d6  mov     rax, rdi
0x18042f2d9  shr     rax, 30h
0x18042f2dd  cmp     rax, 1
0x18042f2e1  jz      loc_18042F4A2
0x18042f2e7  mov     rax, 4000000000000h
0x18042f2f1  cmp     rdi, rax
0x18042f2f4  jnb     loc_18042F4A2
0x18042f2fa  mov     rax, [rdi+8]
0x18042f2fe  cmp     dword ptr [rax], 18h
0x18042f301  jle     loc_18042F4A2
0x18042f307  mov     rsi, [rbx+8]
0x18042f30b  mov     [rsp+0F8h+pv], 0
0x18042f314  mov     [rsp+0F8h+var_B4], 0
0x18042f31c  xorps   xmm0, xmm0
0x18042f31f  movups  [rsp+0F8h+var_98], xmm0
0x18042f324  movups  [rsp+0F8h+var_88], xmm0
0x18042f329  movups  [rsp+0F8h+var_78], xmm0
0x18042f331  lea     rax, [rsp+0F8h]
0x18042f339  mov     r9, [rsp+0F8h]; void *
0x18042f341  mov     [rsp+0F8h+var_C0], 0; bool
0x18042f346  mov     [rsp+0F8h+var_C8], 0; bool
0x18042f34b  mov     [rsp+0F8h+var_D0], 0; bool
0x18042f350  mov     [rsp+0F8h+var_D8], rax; void *
0x18042f355  lea     r8, [rsp+0F8h+var_98]; struct Js::ScriptEntryExitRecord *
0x18042f35a  mov     rdx, rsi; struct Js::ScriptContext *
0x18042f35d  lea     rcx, [rsp+0F8h+var_68]; this
0x18042f365  call    ??0EnterScriptObject@Js@@QEAA@PEAVScriptContext@1@PEAUScriptEntryExitRecord@1@PEAX2_N33@Z; Js::EnterScriptObject::EnterScriptObject(Js::ScriptContext *,Js::ScriptEntryExitRecord *,void *,void *,bool,bool,bool)
0x18042f36a  nop
0x18042f36b  mov     r8b, 1; bool
0x18042f36e  xor     edx, edx; bool
0x18042f370  mov     rcx, rsi; this
0x18042f373  call    ?OnScriptStart@ScriptContext@Js@@QEAAX_N0@Z; Js::ScriptContext::OnScriptStart(bool,bool)
0x18042f378  lea     rcx, [rsp+0F8h+var_68]; this
0x18042f380  call    ?VerifyEnterScript@EnterScriptObject@Js@@QEAAXXZ; Js::EnterScriptObject::VerifyEnterScript(void)
0x18042f385  mov     r8, rsi; struct Js::ScriptContext *
0x18042f388  mov     edx, 0C1h; int
0x18042f38d  mov     rcx, rdi; void *
0x18042f390  call    ?OP_GetProperty@JavascriptOperators@Js@@SAPEAXPEAXHPEAVScriptContext@2@@Z; Js::JavascriptOperators::OP_GetProperty(void *,int,Js::ScriptContext *)
0x18042f395  mov     rdx, rsi; struct Js::ScriptContext *
0x18042f398  mov     rcx, rax; void *
0x18042f39b  call    ?ToLength@JavascriptConversion@Js@@SA_JPEAXPEAVScriptContext@2@@Z; Js::JavascriptConversion::ToLength(void *,Js::ScriptContext *)
0x18042f3a0  mov     rbx, rax
0x18042f3a3  mov     edx, [rsp+0F8h+arg_10]
0x18042f3aa  call    _lambda_6cadc8d183089854dd15570484b09b0b___operator__
0x18042f3af  mov     r8d, eax
0x18042f3b2  mov     eax, 7FFFFFFFh
0x18042f3b7  cdq
0x18042f3b8  idiv    r8d
0x18042f3bb  movsxd  rcx, eax
0x18042f3be  cmp     rbx, rcx
0x18042f3c1  jge     short loc_18042F42B
0x18042f3c3  test    rbx, rbx
0x18042f3c6  js      short loc_18042F42B
0x18042f3c8  mov     [rsp+0F8h+var_B4], ebx
0x18042f3cc  mov     rax, [rsp+0F8h+arg_28]
0x18042f3d4  mov     [rax], r8d
0x18042f3d7  mov     ecx, ebx
0x18042f3d9  imul    ecx, r8d; cb
0x18042f3dd  call    cs:__imp_CoTaskMemAlloc
0x18042f3e4  nop     dword ptr [rax+rax+00h]
0x18042f3e9  mov     [rsp+0F8h+pv], rax
0x18042f3ee  test    rax, rax
0x18042f3f1  jnz     short loc_18042F3FD
0x18042f3f3  mov     [rsp+0F8h+var_B8], 8007000Eh
0x18042f3fb  jmp     short loc_18042F437
0x18042f3fd  mov     qword ptr [rsp+0F8h+var_D0], rsi
0x18042f402  mov     [rsp+0F8h+var_D8], rax
0x18042f407  mov     r9, [rsp+0F8h+arg_28]
0x18042f40f  mov     r9d, [r9]
0x18042f412  mov     r8d, ebx
0x18042f415  mov     edx, [rsp+0F8h+arg_10]
0x18042f41c  mov     rcx, rdi
0x18042f41f  call    ?VarToNativeArray@JavascriptOperators@Js@@SAXPEAXW4JsNativeValueType@@IIPEAEPEAVScriptContext@2@@Z; Js::JavascriptOperators::VarToNativeArray(void *,JsNativeValueType,uint,uint,uchar *,Js::ScriptContext *)
0x18042f424  mov     [rsp+0F8h+var_B8], r14d
0x18042f429  jmp     short loc_18042F437
0x18042f42b  mov     [rsp+0F8h+var_B8], 80070057h
0x18042f433  mov     [rsp+0F8h+var_B4], ebx
0x18042f437  lea     rcx, [rsp+0F8h+var_68]; this
0x18042f43f  call    ??1EnterScriptObject@Js@@QEAA@XZ; Js::EnterScriptObject::~EnterScriptObject(void)
0x18042f444  nop
0x18042f445  jmp     short loc_18042F48D
0x18042f447  mov     rcx, [rsp+0F8h+pv]; pv
0x18042f44c  test    rcx, rcx
0x18042f44f  jz      short loc_18042F45D
0x18042f451  call    cs:__imp_CoTaskMemFree
0x18042f458  nop     dword ptr [rax+rax+00h]
0x18042f45d  mov     rax, [rsp+0F8h+arg_28]
0x18042f465  mov     dword ptr [rax], 0
0x18042f46b  mov     eax, [rsp+0F8h+var_B8]
0x18042f46f  jmp     short loc_18042F4A7
0x18042f471  jmp     short loc_18042F447
0x18042f473  jmp     short loc_18042F447
0x18042f475  jmp     short loc_18042F447
0x18042f477  jmp     short loc_18042F447
0x18042f479  mov     r12, [rsp+0F8h+arg_20]
0x18042f481  mov     r15, [rsp+0F8h+arg_18]
0x18042f489  mov     ebx, [rsp+0F8h+var_B4]
0x18042f48d  cmp     [rsp+0F8h+var_B8], 0
0x18042f492  jl      short loc_18042F447
0x18042f494  mov     rax, [rsp+0F8h+pv]
0x18042f499  mov     [r15], rax
0x18042f49c  mov     [r12], ebx
0x18042f4a0  jmp     short loc_18042F46B
0x18042f4a2  mov     eax, 80070057h
0x18042f4a7  add     rsp, 0C8h
0x18042f4ae  pop     r15
0x18042f4b0  pop     r14
0x18042f4b2  pop     r12
0x18042f4b4  pop     rdi
0x18042f4b5  pop     rsi
0x18042f4b6  pop     rbx
0x18042f4b7  retn
```
