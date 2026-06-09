# CMBPropertyWriter::AddTypeToProperty(PropValue *)

- ea: `0x18002fa90`
- end: `0x18002fb4f`
- name: `?AddTypeToProperty@CMBPropertyWriter@@QEAAJPEAUPropValue@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(CMBPropertyWriter *__hidden this, struct PropValue *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180012938`

## callees

- `0x18002f630`
- `0x18002fa90`
- `0x18003035c`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18002fafa`
- `IisRTL!PuDbgPrintW` at `0x18002fafa`

## string_xrefs

- `0x18002facf`: `CMBPropertyWriter::AddTypeToProperty`
- `0x18002fadd`: `inetsrv\iis\mb\xmlwriter\mbpropertywriter.cpp`

## pseudocode

```c
__int64 __fastcall CMBPropertyWriter::AddTypeToProperty(CMBPropertyWriter *this, struct PropValue *a2)
{
  int v3; // eax
  int v5; // ecx
  __int64 result; // rax
  CMBPropertyWriter *v7; // rbx
  int v8; // [rsp+28h] [rbp-20h]
  int v9; // [rsp+30h] [rbp-18h]
  CMBPropertyWriter *v10; // [rsp+50h] [rbp+8h] BYREF

  *((_QWORD *)this + 2) = a2;
  v3 = *((_DWORD *)a2 + 1);
  if ( !v3 )
    return 0;
  v5 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 == v3 )
    return 0;
  v10 = 0;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v9 = v5;
    v8 = v3;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\xmlwriter\\mbpropertywriter.cpp",
      293,
      "CMBPropertyWriter::AddTypeToProperty",
      L"[AddTypeToProperty] Saving a non-shipped flag. Adding tag ID %d to its property ID %d\n",
      v8,
      v9);
  }
  result = CMBCollectionWriter::GetMBPropertyWriter(*((CMBCollectionWriter **)this + 8), *(_DWORD *)a2, &v10);
  if ( (int)result >= 0 )
  {
    v7 = v10;
    if ( *((_DWORD *)v10 + 12) != *((_DWORD *)v10 + 13) || (int)CMBPropertyWriter::ReAllocate(v10) >= 0 )
      *(_QWORD *)(*((_QWORD *)v7 + 5) + 8LL * (unsigned int)(*((_DWORD *)v7 + 12))++) = this;
    *((_DWORD *)this + 14) = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002fa90  mov     [rsp+arg_8], rbx
0x18002fa95  push    rdi
0x18002fa96  sub     rsp, 40h
0x18002fa9a  mov     [rcx+10h], rdx
0x18002fa9e  mov     rbx, rdx
0x18002faa1  mov     eax, [rdx+4]
0x18002faa4  mov     rdi, rcx
0x18002faa7  test    eax, eax
0x18002faa9  jz      loc_18002FB42
0x18002faaf  mov     ecx, [rdx]
0x18002fab1  cmp     ecx, eax
0x18002fab3  jz      loc_18002FB42
0x18002fab9  test    byte ptr cs:g_dwDebugFlags, 3
0x18002fac0  mov     [rsp+48h+arg_0], 0
0x18002fac9  jz      short loc_18002FB00
0x18002facb  mov     [rsp+48h+var_18], ecx
0x18002facf  lea     r9, aCmbpropertywri_0; "CMBPropertyWriter::AddTypeToProperty"
0x18002fad6  mov     rcx, cs:g_pDebug
0x18002fadd  lea     rdx, aInetsrvIisMbXm_0; "inetsrv\\iis\\mb\\xmlwriter\\mbproperty"...
0x18002fae4  mov     [rsp+48h+var_20], eax
0x18002fae8  mov     r8d, 125h
0x18002faee  lea     rax, aAddtypetoprope; "[AddTypeToProperty] Saving a non-shippe"...
0x18002faf5  mov     [rsp+48h+var_28], rax
0x18002fafa  call    cs:__imp_PuDbgPrintW
0x18002fb00  mov     edx, [rbx]; unsigned int
0x18002fb02  lea     r8, [rsp+48h+arg_0]; struct CMBPropertyWriter **
0x18002fb07  mov     rcx, [rdi+40h]; this
0x18002fb0b  call    ?GetMBPropertyWriter@CMBCollectionWriter@@QEAAJKPEAPEAVCMBPropertyWriter@@@Z; CMBCollectionWriter::GetMBPropertyWriter(ulong,CMBPropertyWriter * *)
0x18002fb10  test    eax, eax
0x18002fb12  js      short loc_18002FB44
0x18002fb14  mov     rbx, [rsp+48h+arg_0]
0x18002fb19  mov     eax, [rbx+34h]
0x18002fb1c  cmp     [rbx+30h], eax
0x18002fb1f  jnz     short loc_18002FB2D
0x18002fb21  mov     rcx, rbx; this
0x18002fb24  call    ?ReAllocate@CMBPropertyWriter@@AEAAJXZ; CMBPropertyWriter::ReAllocate(void)
0x18002fb29  test    eax, eax
0x18002fb2b  js      short loc_18002FB3B
0x18002fb2d  mov     ecx, [rbx+30h]
0x18002fb30  mov     rax, [rbx+28h]
0x18002fb34  mov     [rax+rcx*8], rdi
0x18002fb38  inc     dword ptr [rbx+30h]
0x18002fb3b  mov     dword ptr [rdi+38h], 0
0x18002fb42  xor     eax, eax
0x18002fb44  mov     rbx, [rsp+48h+arg_8]
0x18002fb49  add     rsp, 40h
0x18002fb4d  pop     rdi
0x18002fb4e  retn
```
