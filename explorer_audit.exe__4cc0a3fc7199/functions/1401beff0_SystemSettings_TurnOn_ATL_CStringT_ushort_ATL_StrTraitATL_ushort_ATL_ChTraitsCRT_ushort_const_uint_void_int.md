# SystemSettings::TurnOn(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)

- ea: `0x1401beff0`
- end: `0x1401bf19c`
- name: `?TurnOn@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1401bbfcc`

## callees

- `0x1401040e0`
- `0x1401bedb4`
- `0x1401bef48`
- `0x1401beff0`
- `0x1401d34ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401bf188`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401bf188`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1401bf0d4`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1401bf11a`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1401bf17e`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1401bf0d4`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1401bf11a`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1401bf17e`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendNotifyMessageW` at `0x1401bf134`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendNotifyMessageW` at `0x1401bf134`

## pseudocode

```c
signed int __fastcall SystemSettings::TurnOn(_QWORD *a1, unsigned int a2, UINT *a3, int a4)
{
  __int64 v6; // rbx
  UINT v7; // esi
  unsigned __int16 *v8; // rax
  __int64 v9; // r8
  int v10; // ecx
  int v11; // edx
  signed int result; // eax
  int v13; // ecx
  int v14; // ecx
  UINT v15; // eax
  UINT v16; // ecx
  bool v17; // zf
  UINT *v18; // r8
  UINT v19; // edx
  _OWORD pvParam[4]; // [rsp+20h] [rbp-68h] BYREF

  v6 = 32LL * a2;
  v7 = a4 != 0 ? 3 : 0;
  v8 = *(unsigned __int16 **)((char *)&SystemSettings::_systemSetting + v6);
  v9 = *a1 - (_QWORD)v8;
  do
  {
    v10 = *(unsigned __int16 *)((char *)v8 + v9);
    v11 = *v8 - v10;
    if ( v11 )
      break;
    ++v8;
  }
  while ( v10 );
  if ( v11 )
    return -2147024809;
  if ( wcscmp_0(*(const wchar_t **)((char *)&SystemSettings::_systemSetting + v6), L"animations")
    || (result = SystemSettings::SetAdditionalAnimationSetting((PVOID)*a3), result >= 0) )
  {
    v13 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 16);
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        if ( v14 != 1 )
          return 0;
        v15 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 20);
        if ( !a3 )
        {
          v16 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 8);
          memset(pvParam, 0, 60);
          LODWORD(pvParam[0]) = v15;
          if ( SystemParametersInfoW(v16, v15, pvParam, 0) )
          {
            if ( (BYTE4(pvParam[0]) & 1) == 0 )
            {
              v17 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 12) == 67;
              DWORD1(pvParam[0]) |= 1u;
              if ( v17 && IsInMachineOOBEOrLogonUI() )
                DWORD1(pvParam[0]) |= 0x1000u;
              SystemParametersInfoW(
                *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 12),
                *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 20),
                pvParam,
                v7);
              if ( !a4 )
                SendNotifyMessageW(
                  HWND_BROADCAST,
                  0x1Au,
                  *(unsigned int *)((char *)&SystemSettings::_systemSetting + v6 + 12),
                  0);
            }
            return 0;
          }
          goto LABEL_26;
        }
        *a3 = v15;
        v18 = a3;
      }
      else
      {
        v18 = (UINT *)(int)*a3;
      }
      v19 = *(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 20);
    }
    else
    {
      v18 = *(UINT **)((char *)&SystemSettings::_systemSetting + v6 + 24);
      v19 = *a3;
    }
    if ( !SystemParametersInfoW(*(_DWORD *)((char *)&SystemSettings::_systemSetting + v6 + 12), v19, v18, v7) )
    {
LABEL_26:
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1401beff0  mov     [rsp+arg_0], rbx
0x1401beff5  mov     [rsp+arg_18], rbp
0x1401beffa  push    rsi
0x1401beffb  push    rdi
0x1401beffc  push    r14
0x1401beffe  sub     rsp, 70h
0x1401bf002  mov     rax, cs:__security_cookie
0x1401bf009  xor     rax, rsp
0x1401bf00c  mov     [rsp+88h+var_28], rax
0x1401bf011  mov     eax, r9d
0x1401bf014  mov     ebx, edx
0x1401bf016  neg     eax
0x1401bf018  lea     r14, ?_systemSetting@SystemSettings@@0PAUSystemSetting@@A; SystemSetting near * SystemSettings::_systemSetting
0x1401bf01f  mov     rdi, r8
0x1401bf022  mov     ebp, r9d
0x1401bf025  mov     r8, [rcx]
0x1401bf028  sbb     esi, esi
0x1401bf02a  shl     rbx, 5
0x1401bf02e  and     esi, 3
0x1401bf031  mov     rax, [rbx+r14]
0x1401bf035  sub     r8, rax
0x1401bf038  movzx   edx, word ptr [rax]
0x1401bf03b  movzx   ecx, word ptr [rax+r8]
0x1401bf040  sub     edx, ecx
0x1401bf042  jnz     short loc_1401BF04C
0x1401bf044  add     rax, 2
0x1401bf048  test    ecx, ecx
0x1401bf04a  jnz     short loc_1401BF038
0x1401bf04c  test    edx, edx
0x1401bf04e  jz      short loc_1401BF05A
0x1401bf050  mov     eax, 80070057h
0x1401bf055  jmp     loc_1401BF13C
0x1401bf05a  mov     rcx, [rbx+r14]; String1
0x1401bf05e  lea     rdx, aAnimations; "animations"
0x1401bf065  call    wcscmp_0
0x1401bf06a  test    eax, eax
0x1401bf06c  jnz     short loc_1401BF07D
0x1401bf06e  mov     ecx, [rdi]; pvParam
0x1401bf070  call    ?SetAdditionalAnimationSetting@SystemSettings@@CAJI@Z; SystemSettings::SetAdditionalAnimationSetting(uint)
0x1401bf075  test    eax, eax
0x1401bf077  js      loc_1401BF13C
0x1401bf07d  mov     ecx, [rbx+r14+10h]
0x1401bf082  test    ecx, ecx
0x1401bf084  jz      loc_1401BF16F
0x1401bf08a  sub     ecx, 1
0x1401bf08d  jz      loc_1401BF16A
0x1401bf093  cmp     ecx, 1
0x1401bf096  jnz     loc_1401BF13A
0x1401bf09c  mov     eax, [rbx+r14+14h]
0x1401bf0a1  test    rdi, rdi
0x1401bf0a4  jnz     loc_1401BF15E
0x1401bf0aa  mov     ecx, [rbx+r14+8]; uiAction
0x1401bf0af  lea     r8, [rsp+88h+pvParam]; pvParam
0x1401bf0b4  xorps   xmm0, xmm0
0x1401bf0b7  xor     r9d, r9d; fWinIni
0x1401bf0ba  movups  [rsp+88h+pvParam], xmm0
0x1401bf0bf  mov     edx, eax; uiParam
0x1401bf0c1  mov     dword ptr [rsp+88h+pvParam], eax
0x1401bf0c5  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x1401bf0ca  movups  xmmword ptr [rsp+88h+var_48+0Ch], xmm0
0x1401bf0cf  movups  [rsp+88h+var_58], xmm0
0x1401bf0d4  call    cs:__imp_SystemParametersInfoW
0x1401bf0da  test    eax, eax
0x1401bf0dc  jz      loc_1401BF188
0x1401bf0e2  mov     eax, dword ptr [rsp+88h+pvParam+4]
0x1401bf0e6  test    al, 1
0x1401bf0e8  jnz     short loc_1401BF13A
0x1401bf0ea  or      eax, 1
0x1401bf0ed  cmp     dword ptr [rbx+r14+0Ch], 43h ; 'C'
0x1401bf0f3  mov     dword ptr [rsp+88h+pvParam+4], eax
0x1401bf0f7  jnz     short loc_1401BF108
0x1401bf0f9  call    ?IsInMachineOOBEOrLogonUI@@YA_NXZ; IsInMachineOOBEOrLogonUI(void)
0x1401bf0fe  test    al, al
0x1401bf100  jz      short loc_1401BF108
0x1401bf102  bts     dword ptr [rsp+88h+pvParam+4], 0Ch
0x1401bf108  mov     edx, [rbx+r14+14h]; uiParam
0x1401bf10d  lea     r8, [rsp+88h+pvParam]; pvParam
0x1401bf112  mov     ecx, [rbx+r14+0Ch]; uiAction
0x1401bf117  mov     r9d, esi; fWinIni
0x1401bf11a  call    cs:__imp_SystemParametersInfoW
0x1401bf120  test    ebp, ebp
0x1401bf122  jnz     short loc_1401BF13A
0x1401bf124  mov     r8d, [rbx+r14+0Ch]; wParam
0x1401bf129  lea     edx, [rbp+1Ah]; Msg
0x1401bf12c  xor     r9d, r9d; lParam
0x1401bf12f  mov     ecx, 0FFFFh; hWnd
0x1401bf134  call    cs:__imp_SendNotifyMessageW
0x1401bf13a  xor     eax, eax
0x1401bf13c  mov     rcx, [rsp+88h+var_28]
0x1401bf141  xor     rcx, rsp; StackCookie
0x1401bf144  call    __security_check_cookie
0x1401bf149  lea     r11, [rsp+88h+var_18]
0x1401bf14e  mov     rbx, [r11+20h]
0x1401bf152  mov     rbp, [r11+38h]
0x1401bf156  mov     rsp, r11
0x1401bf159  pop     r14
0x1401bf15b  pop     rdi
0x1401bf15c  pop     rsi
0x1401bf15d  retn
0x1401bf15e  mov     [rdi], eax
0x1401bf160  mov     r8, rdi
0x1401bf163  mov     edx, [rbx+r14+14h]
0x1401bf168  jmp     short loc_1401BF176
0x1401bf16a  movsxd  r8, dword ptr [rdi]
0x1401bf16d  jmp     short loc_1401BF163
0x1401bf16f  mov     r8, [rbx+r14+18h]; pvParam
0x1401bf174  mov     edx, [rdi]; uiParam
0x1401bf176  mov     ecx, [rbx+r14+0Ch]; uiAction
0x1401bf17b  mov     r9d, esi; fWinIni
0x1401bf17e  call    cs:__imp_SystemParametersInfoW
0x1401bf184  test    eax, eax
0x1401bf186  jnz     short loc_1401BF13A
0x1401bf188  call    cs:__imp_GetLastError
0x1401bf18e  test    eax, eax
0x1401bf190  jle     short loc_1401BF13C
0x1401bf192  movzx   eax, ax
0x1401bf195  or      eax, 80070000h
0x1401bf19a  jmp     short loc_1401BF13C
```
