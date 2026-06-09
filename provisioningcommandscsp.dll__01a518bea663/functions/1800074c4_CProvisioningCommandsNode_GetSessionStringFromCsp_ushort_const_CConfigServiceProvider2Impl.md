# CProvisioningCommandsNode::GetSessionStringFromCsp(ushort const *,CConfigServiceProvider2Impl *)

- ea: `0x1800074c4`
- end: `0x18000752a`
- name: `?GetSessionStringFromCsp@CProvisioningCommandsNode@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEAVCConfigServiceProvider2Impl@@@Z`
- size: `102`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, struct CConfigServiceProvider2Impl *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006b10`

## callees

- `0x1800074c4`
- `0x180007530`
- `0x180007c18`

## string_xrefs

- `0x1800074eb`: `TEMPDIR`

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
0x1800074c4  mov     [rsp+arg_0], rcx
0x1800074c9  push    rbx
0x1800074ca  sub     rsp, 40h
0x1800074ce  mov     rax, r8
0x1800074d1  mov     rbx, rcx
0x1800074d4  xorps   xmm0, xmm0
0x1800074d7  xor     ecx, ecx
0x1800074d9  movups  xmmword ptr [rsp+48h+Src], xmm0
0x1800074de  mov     [rsp+48h+var_10], rcx
0x1800074e3  lea     r8, [rsp+48h+Src]; struct tagVARIANT *
0x1800074e8  mov     rdx, rax; struct CConfigServiceProvider2Impl *
0x1800074eb  lea     rcx, ?gc_wszTempDir@@3QBGB; "TEMPDIR"
0x1800074f2  call    ?GetSessionVariableFromCsp@CProvisioningCommandsNode@@CAXPEBGPEAVCConfigServiceProvider2Impl@@PEAUtagVARIANT@@@Z; CProvisioningCommandsNode::GetSessionVariableFromCsp(ushort const *,CConfigServiceProvider2Impl *,tagVARIANT *)
0x1800074f7  mov     rdx, [rsp+48h+Src+8]; Src
0x1800074fc  mov     qword ptr [rbx+18h], 7
0x180007504  mov     qword ptr [rbx+10h], 0
0x18000750c  xor     eax, eax
0x18000750e  mov     [rbx], ax
0x180007511  mov     rcx, rbx; void *
0x180007514  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180007519  mov     rax, rbx
0x18000751c  jmp     short loc_180007523
0x18000751e  mov     rax, [rsp+48h+arg_0]
0x180007523  add     rsp, 40h
0x180007527  pop     rbx
0x180007528  retn
```
