# CProvisioningCommandsNode::GetSessionStringFromCsp(ushort const *,CConfigServiceProvider2Impl *)

- ea: `0x18000781c`
- end: `0x180007882`
- name: `?GetSessionStringFromCsp@CProvisioningCommandsNode@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEAVCConfigServiceProvider2Impl@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006e40`

## callees

- `0x18000781c`
- `0x180007888`
- `0x180007fac`

## string_xrefs

- `0x180007843`: `TEMPDIR`

## pseudocode

```c
_QWORD *__fastcall CProvisioningCommandsNode::GetSessionStringFromCsp(
        _QWORD *a1,
        __int64 a2,
        struct CConfigServiceProvider2Impl *a3)
{
  BSTR bstrVal; // rdx
  _QWORD *result; // rax
  struct tagVARIANT Src; // [rsp+28h] [rbp-20h] BYREF

  memset(&Src, 0, sizeof(Src));
  try
  {
    CProvisioningCommandsNode::GetSessionVariableFromCsp((OLECHAR *)L"TEMPDIR", a3, &Src);
    bstrVal = Src.bstrVal;
    a1[3] = 7;
    a1[2] = 0;
    *(_WORD *)a1 = 0;
    std::wstring::assign(a1, bstrVal);
    result = a1;
  }
  catch ( ... )
  {
    a1[2] = 0;
    a1[3] = 0;
    a1[3] = 7;
    a1[2] = 0;
    *(_WORD *)a1 = 0;
    return a1;
  }
  return result;
}

```

## disassembly

```asm
0x18000781c  mov     [rsp+arg_0], rcx
0x180007821  push    rbx
0x180007822  sub     rsp, 40h
0x180007826  mov     rax, r8
0x180007829  mov     rbx, rcx
0x18000782c  xorps   xmm0, xmm0
0x18000782f  xor     ecx, ecx
0x180007831  movups  xmmword ptr [rsp+48h+Src], xmm0
0x180007836  mov     [rsp+48h+var_10], rcx
0x18000783b  lea     r8, [rsp+48h+Src]; struct tagVARIANT *
0x180007840  mov     rdx, rax; struct CConfigServiceProvider2Impl *
0x180007843  lea     rcx, ?gc_wszTempDir@@3QBGB; "TEMPDIR"
0x18000784a  call    ?GetSessionVariableFromCsp@CProvisioningCommandsNode@@CAXPEBGPEAVCConfigServiceProvider2Impl@@PEAUtagVARIANT@@@Z; CProvisioningCommandsNode::GetSessionVariableFromCsp(ushort const *,CConfigServiceProvider2Impl *,tagVARIANT *)
0x18000784f  mov     rdx, [rsp+48h+Src+8]; Src
0x180007854  mov     qword ptr [rbx+18h], 7
0x18000785c  mov     qword ptr [rbx+10h], 0
0x180007864  xor     eax, eax
0x180007866  mov     [rbx], ax
0x180007869  mov     rcx, rbx; void *
0x18000786c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180007871  mov     rax, rbx
0x180007874  jmp     short loc_18000787B
0x180007876  mov     rax, [rsp+48h+arg_0]
0x18000787b  add     rsp, 40h
0x18000787f  pop     rbx
0x180007880  retn
```
