# RegistryKey::GetRegistryString(ushort const *,ushort const *)

- ea: `0x14002b3c8`
- end: `0x14002b538`
- name: `?GetRegistryString@RegistryKey@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG0@Z`
- size: `368`
- prototype: `_QWORD *__fastcall(HKEY *, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14002a61c`

## callees

- `0x140005c58`
- `0x1400060c4`
- `0x1400234dc`
- `0x14002b3c8`
- `0x14002c3e8`
- `0x140030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b509`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002b43d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002b4b9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002b43d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002b4b9`

## pseudocode

```c
_QWORD *__fastcall RegistryKey::GetRegistryString(HKEY *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v6; // r8
  __int64 v7; // r9
  signed int v8; // edi
  _DWORD *pvData; // r10
  _DWORD *v10; // rcx
  __int64 v11; // rax
  DWORD LastError; // eax
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-30h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp+20h] BYREF
  int v16; // [rsp+9Ch] [rbp+24h]

  v16 = HIDWORD(a4);
  pcbData = 0;
  *a2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !RegGetValueW(*a1, 0, L"Thumbprint", 2u, 0, 0, &pcbData) )
  {
    v8 = pcbData - 1;
    if ( (((*(_DWORD *)(*a2 - 12LL) - (pcbData - 1)) | (1 - *(_DWORD *)(*a2 - 8LL))) & 0x80000000) != 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, (unsigned int)v8, v6, v7);
    if ( v8 >= 0 )
    {
      pvData = (_DWORD *)*a2;
      if ( v8 <= *(_DWORD *)(*a2 - 12LL) )
      {
        *(pvData - 4) = v8;
        *(_WORD *)(*a2 + 2LL * v8) = 0;
        if ( RegGetValueW(*a1, 0, L"Thumbprint", 2u, 0, pvData, &pcbData) )
        {
          LastError = GetLastError();
          Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, LastError);
          throw (Win32Exception *)pExceptionObject;
        }
        v10 = (_DWORD *)*a2;
        if ( *a2 )
        {
          v11 = -1;
          do
            ++v11;
          while ( *((_WORD *)v10 + v11) );
          if ( (int)v11 < 0 )
            goto LABEL_16;
        }
        else
        {
          LODWORD(v11) = 0;
        }
        if ( (int)v11 <= *(v10 - 3) )
        {
          *(v10 - 4) = v11;
          *(_WORD *)(*a2 + 2LL * (unsigned int)v11) = 0;
          return a2;
        }
      }
    }
LABEL_16:
    ATL::AtlThrowImpl(0x80070057);
  }
  return a2;
}

```

## disassembly

```asm
0x14002b3c8  mov     rax, rsp
0x14002b3cb  mov     [rax+8], rbx
0x14002b3cf  mov     [rax+18h], rbp
0x14002b3d3  mov     [rax+20h], r9
0x14002b3d7  mov     [rax+10h], rdx
0x14002b3db  push    rsi
0x14002b3dc  push    rdi
0x14002b3dd  push    r14
0x14002b3df  sub     rsp, 60h
0x14002b3e3  mov     rbx, rdx
0x14002b3e6  mov     r14, rcx
0x14002b3e9  xor     ebp, ebp
0x14002b3eb  mov     [rax-38h], ebp
0x14002b3ee  mov     [rax+20h], ebp
0x14002b3f1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002b3f8  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14002b3ff  mov     rax, [rax+18h]
0x14002b403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b408  add     rax, 18h
0x14002b40c  mov     [rbx], rax
0x14002b40f  lea     esi, [rbp+1]
0x14002b412  mov     [rsp+78h+var_38], esi
0x14002b416  lea     rax, [rsp+78h+arg_18]
0x14002b41e  mov     [rsp+78h+pcbData], rax; pcbData
0x14002b423  mov     [rsp+78h+pvData], rbp; pvData
0x14002b428  mov     [rsp+78h+pdwType], rbp; pdwType
0x14002b42d  lea     r9d, [rbp+2]; dwFlags
0x14002b431  lea     r8, Value; "Thumbprint"
0x14002b438  xor     edx, edx; lpSubKey
0x14002b43a  mov     rcx, [r14]; hkey
0x14002b43d  call    cs:__imp_RegGetValueW
0x14002b443  test    eax, eax
0x14002b445  jnz     loc_14002B4F1
0x14002b44b  mov     edi, [rsp+78h+arg_18]
0x14002b452  dec     edi
0x14002b454  mov     rax, [rbx]
0x14002b457  sub     esi, [rax-8]
0x14002b45a  mov     ecx, [rax-0Ch]
0x14002b45d  sub     ecx, edi
0x14002b45f  or      esi, ecx
0x14002b461  jge     short loc_14002B46D
0x14002b463  mov     edx, edi
0x14002b465  mov     rcx, rbx
0x14002b468  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14002b46d  test    edi, edi
0x14002b46f  js      loc_14002B52D
0x14002b475  mov     r10, [rbx]
0x14002b478  cmp     edi, [r10-0Ch]
0x14002b47c  jg      loc_14002B52D
0x14002b482  mov     [r10-10h], edi
0x14002b486  movsxd  rdx, edi
0x14002b489  mov     rcx, [rbx]
0x14002b48c  mov     [rcx+rdx*2], bp
0x14002b490  lea     rax, [rsp+78h+arg_18]
0x14002b498  mov     [rsp+78h+pcbData], rax; pcbData
0x14002b49d  mov     [rsp+78h+pvData], r10; pvData
0x14002b4a2  mov     [rsp+78h+pdwType], rbp; pdwType
0x14002b4a7  mov     r9d, 2; dwFlags
0x14002b4ad  lea     r8, Value; "Thumbprint"
0x14002b4b4  xor     edx, edx; lpSubKey
0x14002b4b6  mov     rcx, [r14]; hkey
0x14002b4b9  call    cs:__imp_RegGetValueW
0x14002b4bf  test    eax, eax
0x14002b4c1  jnz     short loc_14002B509
0x14002b4c3  mov     rcx, [rbx]
0x14002b4c6  test    rcx, rcx
0x14002b4c9  jnz     short loc_14002B4CF
0x14002b4cb  mov     eax, ebp
0x14002b4cd  jmp     short loc_14002B4E0
0x14002b4cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002b4d3  inc     rax
0x14002b4d6  cmp     [rcx+rax*2], bp
0x14002b4da  jnz     short loc_14002B4D3
0x14002b4dc  test    eax, eax
0x14002b4de  js      short loc_14002B52D
0x14002b4e0  cmp     eax, [rcx-0Ch]
0x14002b4e3  jg      short loc_14002B52D
0x14002b4e5  mov     [rcx-10h], eax
0x14002b4e8  mov     edx, eax
0x14002b4ea  mov     rcx, [rbx]
0x14002b4ed  mov     [rcx+rdx*2], bp
0x14002b4f1  mov     rax, rbx
0x14002b4f4  lea     r11, [rsp+78h+var_18]
0x14002b4f9  mov     rbx, [r11+20h]
0x14002b4fd  mov     rbp, [r11+30h]
0x14002b501  mov     rsp, r11
0x14002b504  pop     r14
0x14002b506  pop     rdi
0x14002b507  pop     rsi
0x14002b508  retn
0x14002b509  call    cs:__imp_GetLastError
0x14002b50f  mov     edx, eax; unsigned int
0x14002b511  lea     rcx, [rsp+78h+pExceptionObject]; this
0x14002b516  call    ??0Win32Exception@@QEAA@K@Z; Win32Exception::Win32Exception(ulong)
0x14002b51b  lea     rdx, _TI2?AVWin32Exception@@; pThrowInfo
0x14002b522  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x14002b527  call    _CxxThrowException_0
0x14002b52d  mov     ecx, 80070057h; unsigned int
0x14002b532  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
