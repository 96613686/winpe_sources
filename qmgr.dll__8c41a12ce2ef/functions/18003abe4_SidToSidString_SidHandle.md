# SidToSidString(SidHandle)

- ea: `0x18003abe4`
- end: `0x18003accf`
- name: `?SidToSidString@@YA?AV?$GenericStringHandle@G@@VSidHandle@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003a1fc`
- `0x18003a860`
- `0x18003bf78`
- `0x18003dd08`
- `0x18004926c`
- `0x180089d4c`
- `0x1800a05d8`
- `0x1800a0698`
- `0x1800cbe68`
- `0x1800d2060`
- `0x1800d2500`

## callees

- `0x180016d60`
- `0x18003abe4`
- `0x18003acd8`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ac38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ac42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ac4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ac38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ac42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ac4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003aca9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003aca9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003ac2e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003ac2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall SidToSidString(_QWORD *a1, PSID *a2)
{
  unsigned int LastError; // eax
  __int64 *v6; // rbp
  EVENT_LOG *v7; // rcx
  ComError *v8; // rax
  void *v9; // rcx
  __int64 *v10; // rdx
  __int64 v11; // [rsp+0h] [rbp-108h] BYREF
  ComError *v12; // [rsp+28h] [rbp-E0h] BYREF
  void **pExceptionObject; // [rsp+30h] [rbp-D8h] BYREF
  __int128 v14; // [rsp+38h] [rbp-D0h]
  unsigned int v15; // [rsp+48h] [rbp-C0h]
  int v16; // [rsp+4Ch] [rbp-BCh]
  int v17; // [rsp+50h] [rbp-B8h]
  HLOCAL hMem; // [rsp+128h] [rbp+20h] BYREF

  hMem = 0;
  _InterlockedIncrement(&dword_180145058);
  *a1 = &GenericStringHandle<unsigned short>::s_EmptyString;
  if ( !ConvertSidToStringSidW(*a2, (LPWSTR *)&hMem) )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    try
    {
      v14 = 0;
      pExceptionObject = &ComError::`vftable';
      v15 = LastError;
      v16 = 1245;
      v17 = 1;
      throw (ComError *)&pExceptionObject;
    }
    catch ( ComError *v12 )
    {
      v10 = &v11;
      v6 = v10;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)v7 + 2), 42, &WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids);
      v8 = ComError::ComError((ComError *)(v6 + 18), (const struct ComError *)v6[5]);
      LogException(v8);
      v9 = (void *)v6[37];
      if ( v9 )
        LocalFree(v9);
      throw;
    }
  }
  GenericStringHandle<unsigned short>::operator=(a1, hMem);
  LocalFree(hMem);
  SidHandle::~SidHandle((SidHandle *)a2);
  return a1;
}

```

## disassembly

```asm
0x18003abe4  mov     r11, rsp
0x18003abe7  mov     [r11+10h], rdx
0x18003abeb  mov     [r11+8], rcx
0x18003abef  push    rbx
0x18003abf0  push    rdi
0x18003abf1  sub     rsp, 0F8h
0x18003abf8  mov     rdi, rdx
0x18003abfb  mov     rbx, rcx
0x18003abfe  mov     dword ptr [r11+18h], 1
0x18003ac06  mov     qword ptr [r11+20h], 0
0x18003ac0e  lock inc cs:dword_180145058
0x18003ac15  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x18003ac1c  mov     [rcx], rax
0x18003ac1f  mov     dword ptr [r11+18h], 1
0x18003ac27  lea     rdx, [r11+20h]; StringSid
0x18003ac2b  mov     rcx, [rdi]; Sid
0x18003ac2e  call    cs:__imp_ConvertSidToStringSidW
0x18003ac34  test    eax, eax
0x18003ac36  jnz     short loc_18003AC91
0x18003ac38  call    cs:__imp_GetLastError
0x18003ac3e  test    eax, eax
0x18003ac40  jg      short loc_18003AC4A
0x18003ac42  call    cs:__imp_GetLastError
0x18003ac48  jmp     short loc_18003AC58
0x18003ac4a  call    cs:__imp_GetLastError
0x18003ac50  movzx   eax, ax
0x18003ac53  or      eax, 80070000h
0x18003ac58  xorps   xmm0, xmm0
0x18003ac5b  movups  [rsp+108h+var_D0], xmm0
0x18003ac60  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003ac67  mov     [rsp+108h+pExceptionObject], rcx
0x18003ac6c  mov     [rsp+108h+var_C0], eax
0x18003ac70  mov     [rsp+108h+var_BC], 4DDh
0x18003ac78  mov     [rsp+108h+var_B8], 1
0x18003ac80  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003ac87  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18003ac8c  call    _CxxThrowException_0
0x18003ac91  mov     rdx, [rsp+108h+hMem]
0x18003ac99  mov     rcx, rbx
0x18003ac9c  call    ??4?$GenericStringHandle@G@@QEAAXPEBG@Z; GenericStringHandle<ushort>::operator=(ushort const *)
0x18003aca1  mov     rcx, [rsp+108h+hMem]; hMem
0x18003aca9  call    cs:__imp_LocalFree
0x18003acaf  mov     [rsp+108h+arg_10], 0
0x18003acba  mov     rcx, rdi; this
0x18003acbd  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x18003acc2  mov     rax, rbx
0x18003acc5  add     rsp, 0F8h
0x18003accc  pop     rdi
0x18003accd  pop     rbx
0x18003acce  retn
```
