# SystemSettings::TurnOff(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)

- ea: `0x140021e5c`
- end: `0x140021f7b`
- name: `?TurnOff@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140020d24`

## callees

- `0x140021c20`
- `0x140021e5c`
- `0x140025d70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140021efa`
- `KERNEL32!GetLastError` at `0x140021efa`
- `USER32!SystemParametersInfoW` at `0x140021ef0`
- `USER32!SystemParametersInfoW` at `0x140021f43`
- `USER32!SystemParametersInfoW` at `0x140021ef0`
- `USER32!SystemParametersInfoW` at `0x140021f43`
- `USER32!SendNotifyMessageW` at `0x140021f5d`
- `USER32!SendNotifyMessageW` at `0x140021f5d`

## pseudocode

```c
signed int __fastcall SystemSettings::TurnOff(_QWORD *a1, unsigned int a2, __int64 a3, int a4)
{
  __int64 v5; // rbx
  UINT v6; // edi
  unsigned __int16 *v7; // rax
  __int64 v8; // r8
  int v9; // ecx
  int v10; // edx
  signed int result; // eax
  UINT v12; // edx
  UINT v13; // ecx
  bool v14; // zf
  _OWORD pvParam[4]; // [rsp+20h] [rbp-78h] BYREF

  v5 = 32LL * a2;
  v6 = a4 != 0 ? 3 : 0;
  v7 = *(unsigned __int16 **)((char *)&SystemSettings::_systemSetting + v5);
  v8 = *a1 - (_QWORD)v7;
  do
  {
    v9 = *(unsigned __int16 *)((char *)v7 + v8);
    v10 = *v7 - v9;
    if ( v10 )
      break;
    ++v7;
  }
  while ( v9 );
  if ( v10 )
    return -2147024809;
  if ( *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 16) != 2 )
    return 0;
  v12 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 20);
  v13 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 8);
  memset(pvParam, 0, 60);
  LODWORD(pvParam[0]) = v12;
  if ( SystemParametersInfoW(v13, v12, pvParam, 0) )
  {
    if ( (BYTE4(pvParam[0]) & 1) != 0 )
    {
      v14 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 12) == 67;
      DWORD1(pvParam[0]) &= ~1u;
      if ( v14 && IsInMachineOOBEOrLogonUI() )
        DWORD1(pvParam[0]) |= 0x1000u;
      SystemParametersInfoW(
        *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 12),
        *(_DWORD *)((char *)&SystemSettings::_systemSetting + v5 + 20),
        pvParam,
        v6);
      if ( !a4 )
        SendNotifyMessageW(
          HWND_BROADCAST,
          0x1Au,
          *(unsigned int *)((char *)&SystemSettings::_systemSetting + v5 + 12),
          0);
    }
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140021e5c  push    rbx
0x140021e5e  push    rbp
0x140021e5f  push    rsi
0x140021e60  push    rdi
0x140021e61  sub     rsp, 78h
0x140021e65  mov     rax, cs:__security_cookie
0x140021e6c  xor     rax, rsp
0x140021e6f  mov     [rsp+98h+var_38], rax
0x140021e74  mov     r8, [rcx]
0x140021e77  lea     rbp, ?_systemSetting@SystemSettings@@0PAUSystemSetting@@A; SystemSetting near * SystemSettings::_systemSetting
0x140021e7e  mov     eax, r9d
0x140021e81  mov     ebx, edx
0x140021e83  neg     eax
0x140021e85  mov     esi, r9d
0x140021e88  sbb     edi, edi
0x140021e8a  shl     rbx, 5
0x140021e8e  and     edi, 3
0x140021e91  mov     rax, [rbx+rbp]
0x140021e95  sub     r8, rax
0x140021e98  movzx   edx, word ptr [rax]
0x140021e9b  movzx   ecx, word ptr [rax+r8]
0x140021ea0  sub     edx, ecx
0x140021ea2  jnz     short loc_140021EAC
0x140021ea4  add     rax, 2
0x140021ea8  test    ecx, ecx
0x140021eaa  jnz     short loc_140021E98
0x140021eac  test    edx, edx
0x140021eae  jz      short loc_140021EBA
0x140021eb0  mov     eax, 80070057h
0x140021eb5  jmp     loc_140021F65
0x140021eba  cmp     dword ptr [rbx+rbp+10h], 2
0x140021ebf  jnz     loc_140021F63
0x140021ec5  mov     edx, [rbx+rbp+14h]; uiParam
0x140021ec9  lea     r8, [rsp+98h+pvParam]; pvParam
0x140021ece  mov     ecx, [rbx+rbp+8]; uiAction
0x140021ed2  xorps   xmm0, xmm0
0x140021ed5  movups  [rsp+98h+pvParam], xmm0
0x140021eda  xor     r9d, r9d; fWinIni
0x140021edd  mov     dword ptr [rsp+98h+pvParam], edx
0x140021ee1  movups  xmmword ptr [rsp+98h+var_58], xmm0
0x140021ee6  movups  xmmword ptr [rsp+98h+var_58+0Ch], xmm0
0x140021eeb  movups  [rsp+98h+var_68], xmm0
0x140021ef0  call    cs:__imp_SystemParametersInfoW
0x140021ef6  test    eax, eax
0x140021ef8  jnz     short loc_140021F0E
0x140021efa  call    cs:__imp_GetLastError
0x140021f00  test    eax, eax
0x140021f02  jle     short loc_140021F65
0x140021f04  movzx   eax, ax
0x140021f07  or      eax, 80070000h
0x140021f0c  jmp     short loc_140021F65
0x140021f0e  mov     eax, dword ptr [rsp+98h+pvParam+4]
0x140021f12  test    al, 1
0x140021f14  jz      short loc_140021F63
0x140021f16  and     eax, 0FFFFFFFEh
0x140021f19  cmp     dword ptr [rbx+rbp+0Ch], 43h ; 'C'
0x140021f1e  mov     dword ptr [rsp+98h+pvParam+4], eax
0x140021f22  jnz     short loc_140021F33
0x140021f24  call    ?IsInMachineOOBEOrLogonUI@@YA_NXZ; IsInMachineOOBEOrLogonUI(void)
0x140021f29  test    al, al
0x140021f2b  jz      short loc_140021F33
0x140021f2d  bts     dword ptr [rsp+98h+pvParam+4], 0Ch
0x140021f33  mov     edx, [rbx+rbp+14h]; uiParam
0x140021f37  lea     r8, [rsp+98h+pvParam]; pvParam
0x140021f3c  mov     ecx, [rbx+rbp+0Ch]; uiAction
0x140021f40  mov     r9d, edi; fWinIni
0x140021f43  call    cs:__imp_SystemParametersInfoW
0x140021f49  test    esi, esi
0x140021f4b  jnz     short loc_140021F63
0x140021f4d  mov     r8d, [rbx+rbp+0Ch]; wParam
0x140021f52  lea     edx, [rsi+1Ah]; Msg
0x140021f55  xor     r9d, r9d; lParam
0x140021f58  mov     ecx, 0FFFFh; hWnd
0x140021f5d  call    cs:__imp_SendNotifyMessageW
0x140021f63  xor     eax, eax
0x140021f65  mov     rcx, [rsp+98h+var_38]
0x140021f6a  xor     rcx, rsp; StackCookie
0x140021f6d  call    __security_check_cookie
0x140021f72  add     rsp, 78h
0x140021f76  pop     rdi
0x140021f77  pop     rsi
0x140021f78  pop     rbp
0x140021f79  pop     rbx
0x140021f7a  retn
```
