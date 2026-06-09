# CertificateStore::Purge(void)

- ea: `0x18002156c`
- end: `0x180021610`
- name: `?Purge@CertificateStore@@QEAAXXZ`
- size: `164`
- prototype: `void __fastcall(CertificateStore *this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180021618`
- `0x1800258c0`

## callees

- `0x1800032f4`
- `0x18000fa6c`
- `0x180012770`
- `0x180013bdc`
- `0x180021538`
- `0x18002156c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180021593`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180021593`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CertificateStore::Purge(CertificateStore *this)
{
  LSTATUS v1; // eax
  signed int v2; // ebx
  std::shared_ptr<Registry::Key> key; // [rsp+20h] [rbp-38h] BYREF
  HrException pExceptionObject; // [rsp+30h] [rbp-28h] BYREF

  key = 0;
  anonymous_namespace_::GetKey(&key, &this->m_opaqueKey);
  v1 = RegDeleteTreeW(key._Ptr->m_keyHandle, 0);
  v2 = v1;
  if ( v1 > 0 )
    v2 = (unsigned __int16)v1 | 0x80070000;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x12u, WPP_ab8b6079818734ffc464e1b7e922f159_Traceguids, v2);
    }
    HrException::HrException(&pExceptionObject, v2);
    throw &pExceptionObject;
  }
  if ( key._Rep )
    std::_Ref_count_base::_Decref(key._Rep);
}

```

## disassembly

```asm
0x18002156c  push    rbx
0x18002156e  sub     rsp, 50h
0x180021572  xorps   xmm0, xmm0
0x180021575  movups  xmmword ptr [rsp+58h+key._Ptr], xmm0
0x18002157a  lea     rdx, [this+20h]; spv
0x18002157e  lea     this, [rsp+58h+key]; result
0x180021583  call    _anonymous_namespace___GetKey
0x180021588  nop
0x180021589  xor     edx, edx; lpSubKey
0x18002158b  mov     this, [rsp+58h+key._Ptr]
0x180021590  mov     this, [this]; hKey
0x180021593  call    cs:__imp_RegDeleteTreeW
0x180021599  mov     ebx, eax
0x18002159b  test    eax, eax
0x18002159d  jle     short loc_1800215A8
0x18002159f  movzx   ebx, ax
0x1800215a2  or      ebx, 80070000h
0x1800215a8  test    ebx, ebx
0x1800215aa  jns     short loc_1800215FB
0x1800215ac  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x1800215b3  mov     this, cs:WPP_GLOBAL_Control
0x1800215ba  cmp     this, rax
0x1800215bd  jz      short loc_1800215DD
0x1800215bf  test    byte ptr [this+1Ch], 2
0x1800215c3  jz      short loc_1800215DD
0x1800215c5  mov     edx, 12h; id
0x1800215ca  mov     r9d, ebx; _a1
0x1800215cd  lea     r8, WPP_ab8b6079818734ffc464e1b7e922f159_Traceguids; TraceGuid
0x1800215d4  mov     this, [this+10h]; Logger
0x1800215d8  call    WPP_SF_d
0x1800215dd  mov     edx, ebx; ErrorCode
0x1800215df  lea     this, [rsp+58h+pExceptionObject]; this
0x1800215e4  call    ??0HrException@@QEAA@J@Z; HrException::HrException(long)
0x1800215e9  lea     rdx, _TI2?AVHrException@@; pThrowInfo
0x1800215f0  lea     this, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800215f5  call    _CxxThrowException_0
0x1800215fb  mov     this, [rsp+58h+key._Rep]; this
0x180021600  test    this, this
0x180021603  jz      short loc_18002160A
0x180021605  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002160a  add     rsp, 50h
0x18002160e  pop     rbx
0x18002160f  retn
```
