# PerfDiagDm::GetResolverDataFilename(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,_GUID const &)

- ea: `0x1800be2f4`
- end: `0x1800be3dd`
- name: `?GetResolverDataFilename@PerfDiagDm@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBU_GUID@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180043150`
- `0x180043aac`
- `0x1800b24c4`
- `0x1800b736c`
- `0x1800baa4c`
- `0x1800bad48`

## callees

- `0x18001890c`
- `0x180019370`
- `0x18008dc04`
- `0x1800be2f4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800be314`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800be32e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800be314`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800be32e`

## pseudocode

```c
__int64 __fastcall PerfDiagDm::GetResolverDataFilename(__int64 a1, unsigned int *a2)
{
  UINT SystemDirectoryW; // eax
  UINT v5; // ebx
  WCHAR *BufferSetLength; // rax
  UINT v7; // edi
  UINT v8; // eax
  __int64; // rax
  int v10; // [rsp+20h] [rbp-78h]
  int v11; // [rsp+28h] [rbp-70h]
  int v12; // [rsp+30h] [rbp-68h]
  int v13; // [rsp+38h] [rbp-60h]
  int v14; // [rsp+40h] [rbp-58h]
  int v15; // [rsp+48h] [rbp-50h]
  int v16; // [rsp+50h] [rbp-48h]
  int v17; // [rsp+58h] [rbp-40h]
  int v18; // [rsp+60h] [rbp-38h]
  ATL::CAtlException *v19; // [rsp+70h] [rbp-28h] BYREF

  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v5 = SystemDirectoryW;
    BufferSetLength = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(a1, SystemDirectoryW);
    v7 = v5 - 1;
    v8 = GetSystemDirectoryW(BufferSetLength, v5);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v19) )
    {
       = *(unsigned int *)v19;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800BE3BC);
      return ;
    }
  }
  if ( v7 != v8 )
    return 2147549183LL;
  ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, v7);
  v18 = *((unsigned __int8 *)a2 + 15);
  v17 = *((unsigned __int8 *)a2 + 14);
  v16 = *((unsigned __int8 *)a2 + 13);
  v15 = *((unsigned __int8 *)a2 + 12);
  v14 = *((unsigned __int8 *)a2 + 11);
  v13 = *((unsigned __int8 *)a2 + 10);
  v12 = *((unsigned __int8 *)a2 + 9);
  v11 = *((unsigned __int8 *)a2 + 8);
  v10 = *((unsigned __int16 *)a2 + 3);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    a1,
    L"\\WDI\\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}.bin",
    *a2,
    *((unsigned __int16 *)a2 + 2),
    v10,
    v11,
    v12,
    v13,
    v14,
    v15,
    v16,
    v17,
    v18);
  return 0;
}

```

## disassembly

```asm
0x1800be2f4  mov     [rsp+arg_0], rbx
0x1800be2f9  mov     [rsp+arg_8], rsi
0x1800be2fe  push    rdi
0x1800be2ff  push    r14
0x1800be301  push    r15
0x1800be303  sub     rsp, 80h
0x1800be30a  mov     r14, rdx
0x1800be30d  mov     r15, rcx
0x1800be310  xor     edx, edx; uSize
0x1800be312  xor     ecx, ecx; lpBuffer
0x1800be314  call    cs:__imp_GetSystemDirectoryW
0x1800be31a  mov     ebx, eax
0x1800be31c  mov     edx, eax
0x1800be31e  mov     rcx, r15
0x1800be321  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x1800be326  lea     edi, [rbx-1]
0x1800be329  mov     edx, ebx; uSize
0x1800be32b  mov     rcx, rax; lpBuffer
0x1800be32e  call    cs:__imp_GetSystemDirectoryW
0x1800be334  cmp     edi, eax
0x1800be336  jz      short loc_1800BE342
0x1800be338  mov     eax, 8000FFFFh
0x1800be33d  jmp     loc_1800BE3C3
0x1800be342  mov     edx, edi
0x1800be344  mov     rcx, r15
0x1800be347  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800be34c  movzx   eax, byte ptr [r14+0Fh]
0x1800be351  movzx   ecx, byte ptr [r14+0Eh]
0x1800be356  movzx   edx, byte ptr [r14+0Dh]
0x1800be35b  movzx   r8d, byte ptr [r14+0Ch]
0x1800be360  movzx   r10d, byte ptr [r14+0Bh]
0x1800be365  movzx   r11d, byte ptr [r14+0Ah]
0x1800be36a  movzx   ebx, byte ptr [r14+9]
0x1800be36f  movzx   edi, byte ptr [r14+8]
0x1800be374  movzx   esi, word ptr [r14+6]
0x1800be379  movzx   r9d, word ptr [r14+4]
0x1800be37e  mov     [rsp+98h+var_38], eax
0x1800be382  mov     [rsp+98h+var_40], ecx
0x1800be386  mov     [rsp+98h+var_48], edx
0x1800be38a  mov     [rsp+98h+var_50], r8d
0x1800be38f  mov     [rsp+98h+var_58], r10d
0x1800be394  mov     [rsp+98h+var_60], r11d
0x1800be399  mov     [rsp+98h+var_68], ebx
0x1800be39d  mov     [rsp+98h+var_70], edi
0x1800be3a1  mov     [rsp+98h+var_78], esi
0x1800be3a5  mov     r8d, [r14]
0x1800be3a8  lea     rdx, aWdi08x04x04x02; "\\WDI\\{%08x-%04x-%04x-%02x%02x-%02x%02"...
0x1800be3af  mov     rcx, r15
0x1800be3b2  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800be3b7  nop
0x1800be3b8  xor     eax, eax
0x1800be3ba  jmp     short loc_1800BE3C3
0x1800be3bc  mov     eax, [rsp+98h+arg_10]
0x1800be3c3  lea     r11, [rsp+98h+var_18]
0x1800be3cb  mov     rbx, [r11+20h]
0x1800be3cf  mov     rsi, [r11+28h]
0x1800be3d3  mov     rsp, r11
0x1800be3d6  pop     r15
0x1800be3d8  pop     r14
0x1800be3da  pop     rdi
0x1800be3db  retn
```
