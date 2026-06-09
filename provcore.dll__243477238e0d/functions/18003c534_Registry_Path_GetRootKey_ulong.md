# Registry::Path::GetRootKey(ulong)

- ea: `0x18003c534`
- end: `0x18003c5d3`
- name: `?GetRootKey@Path@Registry@@QEBAPEAUHKEY__@@K@Z`
- size: `159`
- prototype: `HKEY__ *__fastcall(Registry::Path *this, unsigned int KeyAccess)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003be7c`
- `0x18003c06c`
- `0x18003ca20`

## callees

- `0x1800032f4`
- `0x180012770`
- `0x18003bc8c`
- `0x18003c534`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18003c558`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18003c558`

## pseudocode

```c
HKEY__ *__fastcall Registry::Path::GetRootKey(Registry::Path *this, REGSAM KeyAccess)
{
  HKEY__ **p_m_hkcuRootKey; // rdi
  int v3; // ebx
  Registry::Exception pExceptionObject; // [rsp+20h] [rbp-28h] BYREF

  if ( this->m_rootKey != (HKEY__ *)-2147483647LL )
    return this->m_rootKey;
  p_m_hkcuRootKey = &this->m_hkcuRootKey;
  if ( !this->m_hkcuRootKey )
  {
    v3 = RegOpenCurrentUser(KeyAccess, &this->m_hkcuRootKey);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x17u, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids, v3);
      }
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      Registry::Exception::Exception(&pExceptionObject, v3);
      throw &pExceptionObject;
    }
  }
  return *p_m_hkcuRootKey;
}

```

## disassembly

```asm
0x18003c534  mov     [rsp+arg_0], rbx
0x18003c539  push    rdi
0x18003c53a  sub     rsp, 40h
0x18003c53e  cmp     qword ptr [this], 0FFFFFFFF80000001h
0x18003c545  mov     eax, KeyAccess
0x18003c547  jnz     short loc_18003C5C5
0x18003c549  lea     rdi, [this+8]
0x18003c54d  cmp     qword ptr [rdi], 0
0x18003c551  jnz     short loc_18003C5C0
0x18003c553  mov     rdx, rdi; phkResult
0x18003c556  mov     ecx, eax; samDesired
0x18003c558  call    cs:__imp_RegOpenCurrentUser
0x18003c55e  mov     ebx, eax
0x18003c560  test    eax, eax
0x18003c562  jz      short loc_18003C5C0
0x18003c564  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003c56b  lea     rax, WPP_GLOBAL_Control
0x18003c572  cmp     this, rax
0x18003c575  jz      short loc_18003C595
0x18003c577  test    byte ptr [this+1Ch], 2
0x18003c57b  jz      short loc_18003C595
0x18003c57d  mov     this, [this+10h]; Logger
0x18003c581  lea     r8, WPP_170303dbc4e93be116a24b4d7c6c7bfc_Traceguids; TraceGuid
0x18003c588  mov     KeyAccess, 17h; id
0x18003c58d  mov     r9d, ebx; _a1
0x18003c590  call    WPP_SF_d
0x18003c595  test    ebx, ebx
0x18003c597  jle     short loc_18003C5A2
0x18003c599  movzx   ebx, bx
0x18003c59c  or      ebx, 80070000h
0x18003c5a2  mov     KeyAccess, ebx; hr
0x18003c5a4  lea     this, [rsp+48h+pExceptionObject]; this
0x18003c5a9  call    ??0Exception@Registry@@QEAA@J@Z; Registry::Exception::Exception(long)
0x18003c5ae  lea     rdx, _TI3?AVException@Registry@@; pThrowInfo
0x18003c5b5  lea     this, [rsp+48h+pExceptionObject]; pExceptionObject
0x18003c5ba  call    _CxxThrowException_0
0x18003c5c0  mov     rax, [rdi]
0x18003c5c3  jmp     short loc_18003C5C8
0x18003c5c5  mov     rax, [this]
0x18003c5c8  mov     rbx, [rsp+48h+arg_0]
0x18003c5cd  add     rsp, 40h
0x18003c5d1  pop     rdi
0x18003c5d2  retn
```
