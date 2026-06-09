# CRegistry::Init(HKEY__ *,wchar_t const *,ulong,wchar_t const *)

- ea: `0x18001de28`
- end: `0x18001df01`
- name: `?Init@CRegistry@@QEAAJPEAUHKEY__@@PEB_WK1@Z`
- size: `217`
- prototype: `int(CRegistry *__hidden this, HKEY, const wchar_t *, unsigned int, const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000ec40`
- `0x18001e9ec`

## callees

- `0x180006430`
- `0x18000a100`
- `0x18000a210`
- `0x18000e488`
- `0x18001de28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001de68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001de68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001de55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001de55`

## pseudocode

```c
__int64 __fastcall CRegistry::Init(CRegistry *this, HKEY a2, wchar_t *a3, REGSAM a4, const wchar_t *a5)
{
  HKEY v9; // rcx
  const wchar_t *v10; // rcx
  __int64 v11; // r9
  LSTATUS v12; // eax
  signed int v13; // ebx
  struct CLMString *v14; // rdi
  ATL::CAtlException *v16; // [rsp+30h] [rbp-38h] BYREF

  if ( *((_DWORD *)this + 42) )
  {
    v9 = (HKEY)*((_QWORD *)this + 22);
    if ( v9 )
    {
      RegCloseKey(v9);
      *((_QWORD *)this + 22) = 0;
    }
  }
  SetLastError(0);
  *((_DWORD *)this + 42) = 1;
  v12 = WSearchRegOpenKeyEx(v10, a2, a3, v11, a4, (HKEY *)this + 22);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( v13 < 0 )
    *((_QWORD *)this + 22) = 0;
  try
  {
    v14 = (CRegistry *)((char *)this + 8);
    if ( a5 )
    {
      CLMString::operator=((__int64)v14, (__int64)a5);
      AppendSlashIf(v14);
      CLMString::Append(v14, a3, 0xFFFFFFFF);
    }
    else
    {
      CLMString::operator=((__int64)v14, (__int64)a3);
    }
  }
  catch ( ATL::CAtlException *v16 )
  {
    return *(unsigned int *)v16;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>();
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001de28  push    rbx
0x18001de2a  push    rsi
0x18001de2b  push    rdi
0x18001de2c  push    r14
0x18001de2e  push    r15
0x18001de30  sub     rsp, 40h
0x18001de34  mov     ebx, r9d
0x18001de37  mov     rsi, r8
0x18001de3a  mov     r15, rdx
0x18001de3d  mov     rdi, rcx
0x18001de40  cmp     dword ptr [rcx+0A8h], 0
0x18001de47  jz      short loc_18001DE66
0x18001de49  mov     rcx, [rcx+0B0h]; hKey
0x18001de50  test    rcx, rcx
0x18001de53  jz      short loc_18001DE66
0x18001de55  call    cs:__imp_RegCloseKey
0x18001de5b  mov     qword ptr [rdi+0B0h], 0
0x18001de66  xor     ecx, ecx; dwErrCode
0x18001de68  call    cs:__imp_SetLastError
0x18001de6e  mov     dword ptr [rdi+0A8h], 1
0x18001de78  lea     r14, [rdi+0B0h]
0x18001de7f  mov     [rsp+68h+var_40], r14; HKEY *
0x18001de84  mov     [rsp+68h+var_48], ebx; unsigned int
0x18001de88  mov     r8, rsi; wchar_t *
0x18001de8b  mov     rdx, r15; HKEY
0x18001de8e  call    ?WSearchRegOpenKeyEx@@YAJPEB_WPEAUHKEY__@@0KKPEAPEAU1@@Z; WSearchRegOpenKeyEx(wchar_t const *,HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x18001de93  mov     ebx, eax
0x18001de95  test    eax, eax
0x18001de97  jle     short loc_18001DEA2
0x18001de99  movzx   ebx, ax
0x18001de9c  or      ebx, 80070000h
0x18001dea2  test    ebx, ebx
0x18001dea4  jns     short loc_18001DEAD
0x18001dea6  mov     qword ptr [r14], 0
0x18001dead  add     rdi, 8
0x18001deb1  mov     rdx, [rsp+68h+arg_20]
0x18001deb9  mov     rcx, rdi
0x18001debc  test    rdx, rdx
0x18001debf  jz      short loc_18001DEDF
0x18001dec1  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001dec6  mov     rcx, rdi; this
0x18001dec9  call    ?AppendSlashIf@@YAXAEAVCLMString@@@Z; AppendSlashIf(CLMString &)
0x18001dece  or      r8d, 0FFFFFFFFh; unsigned int
0x18001ded2  mov     rdx, rsi; wchar_t *
0x18001ded5  mov     rcx, rdi; this
0x18001ded8  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x18001dedd  jmp     short loc_18001DEE8
0x18001dedf  mov     rdx, rsi
0x18001dee2  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18001dee7  nop
0x18001dee8  jmp     short loc_18001DEF3
0x18001deea  jmp     short $+2
0x18001deec  mov     ebx, dword ptr [rsp+68h+arg_20]
0x18001def3  mov     eax, ebx
0x18001def5  add     rsp, 40h
0x18001def9  pop     r15
0x18001defb  pop     r14
0x18001defd  pop     rdi
0x18001defe  pop     rsi
0x18001deff  pop     rbx
0x18001df00  retn
```
