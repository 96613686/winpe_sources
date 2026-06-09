# SystemSettings::TurnOn(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)

- ea: `0x1401bd6f0`
- end: `0x1401bd8bb`
- name: `?TurnOn@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1401ba634`

## callees

- `0x14010e160`
- `0x1401bd478`
- `0x1401bd634`
- `0x1401bd6f0`
- `0x1401d1e34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401bd8a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401bd8a1`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1401bd7d4`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1401bd820`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1401bd891`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1401bd7d4`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1401bd820`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1401bd891`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendNotifyMessageW` at `0x1401bd840`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendNotifyMessageW` at `0x1401bd840`

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
0x1401bd6f0  mov     [rsp+arg_0], rbx
0x1401bd6f5  mov     [rsp+arg_18], rbp
0x1401bd6fa  push    rsi
0x1401bd6fb  push    rdi
0x1401bd6fc  push    r14
0x1401bd6fe  sub     rsp, 70h
0x1401bd702  mov     rax, cs:__security_cookie
0x1401bd709  xor     rax, rsp
0x1401bd70c  mov     [rsp+88h+var_28], rax
0x1401bd711  mov     eax, r9d
0x1401bd714  mov     ebx, edx
0x1401bd716  neg     eax
0x1401bd718  lea     r14, ?_systemSetting@SystemSettings@@0PAUSystemSetting@@A; SystemSetting near * SystemSettings::_systemSetting
0x1401bd71f  mov     rdi, r8
0x1401bd722  mov     ebp, r9d
0x1401bd725  mov     r8, [rcx]
0x1401bd728  sbb     esi, esi
0x1401bd72a  shl     rbx, 5
0x1401bd72e  and     esi, 3
0x1401bd731  mov     rax, [rbx+r14]
0x1401bd735  sub     r8, rax
0x1401bd738  movzx   edx, word ptr [rax]
0x1401bd73b  movzx   ecx, word ptr [rax+r8]
0x1401bd740  sub     edx, ecx
0x1401bd742  jnz     short loc_1401BD74C
0x1401bd744  add     rax, 2
0x1401bd748  test    ecx, ecx
0x1401bd74a  jnz     short loc_1401BD738
0x1401bd74c  test    edx, edx
0x1401bd74e  jz      short loc_1401BD75A
0x1401bd750  mov     eax, 80070057h
0x1401bd755  jmp     loc_1401BD84E
0x1401bd75a  mov     rcx, [rbx+r14]; String1
0x1401bd75e  lea     rdx, aAnimations; "animations"
0x1401bd765  call    wcscmp_0
0x1401bd76a  test    eax, eax
0x1401bd76c  jnz     short loc_1401BD77D
0x1401bd76e  mov     ecx, [rdi]; pvParam
0x1401bd770  call    ?SetAdditionalAnimationSetting@SystemSettings@@CAJI@Z; SystemSettings::SetAdditionalAnimationSetting(uint)
0x1401bd775  test    eax, eax
0x1401bd777  js      loc_1401BD84E
0x1401bd77d  mov     ecx, [rbx+r14+10h]
0x1401bd782  test    ecx, ecx
0x1401bd784  jz      loc_1401BD882
0x1401bd78a  sub     ecx, 1
0x1401bd78d  jz      loc_1401BD87D
0x1401bd793  cmp     ecx, 1
0x1401bd796  jnz     loc_1401BD84C
0x1401bd79c  mov     eax, [rbx+r14+14h]
0x1401bd7a1  test    rdi, rdi
0x1401bd7a4  jnz     loc_1401BD871
0x1401bd7aa  mov     ecx, [rbx+r14+8]; uiAction
0x1401bd7af  lea     r8, [rsp+88h+pvParam]; pvParam
0x1401bd7b4  xorps   xmm0, xmm0
0x1401bd7b7  xor     r9d, r9d; fWinIni
0x1401bd7ba  movups  [rsp+88h+pvParam], xmm0
0x1401bd7bf  mov     edx, eax; uiParam
0x1401bd7c1  mov     dword ptr [rsp+88h+pvParam], eax
0x1401bd7c5  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x1401bd7ca  movups  xmmword ptr [rsp+88h+var_48+0Ch], xmm0
0x1401bd7cf  movups  [rsp+88h+var_58], xmm0
0x1401bd7d4  call    cs:__imp_SystemParametersInfoW
0x1401bd7db  nop     dword ptr [rax+rax+00h]
0x1401bd7e0  test    eax, eax
0x1401bd7e2  jz      loc_1401BD8A1
0x1401bd7e8  mov     eax, dword ptr [rsp+88h+pvParam+4]
0x1401bd7ec  test    al, 1
0x1401bd7ee  jnz     short loc_1401BD84C
0x1401bd7f0  or      eax, 1
0x1401bd7f3  cmp     dword ptr [rbx+r14+0Ch], 43h ; 'C'
0x1401bd7f9  mov     dword ptr [rsp+88h+pvParam+4], eax
0x1401bd7fd  jnz     short loc_1401BD80E
0x1401bd7ff  call    ?IsInMachineOOBEOrLogonUI@@YA_NXZ; IsInMachineOOBEOrLogonUI(void)
0x1401bd804  test    al, al
0x1401bd806  jz      short loc_1401BD80E
0x1401bd808  bts     dword ptr [rsp+88h+pvParam+4], 0Ch
0x1401bd80e  mov     edx, [rbx+r14+14h]; uiParam
0x1401bd813  lea     r8, [rsp+88h+pvParam]; pvParam
0x1401bd818  mov     ecx, [rbx+r14+0Ch]; uiAction
0x1401bd81d  mov     r9d, esi; fWinIni
0x1401bd820  call    cs:__imp_SystemParametersInfoW
0x1401bd827  nop     dword ptr [rax+rax+00h]
0x1401bd82c  test    ebp, ebp
0x1401bd82e  jnz     short loc_1401BD84C
0x1401bd830  mov     r8d, [rbx+r14+0Ch]; wParam
0x1401bd835  lea     edx, [rbp+1Ah]; Msg
0x1401bd838  xor     r9d, r9d; lParam
0x1401bd83b  mov     ecx, 0FFFFh; hWnd
0x1401bd840  call    cs:__imp_SendNotifyMessageW
0x1401bd847  nop     dword ptr [rax+rax+00h]
0x1401bd84c  xor     eax, eax
0x1401bd84e  mov     rcx, [rsp+88h+var_28]
0x1401bd853  xor     rcx, rsp; StackCookie
0x1401bd856  call    __security_check_cookie
0x1401bd85b  lea     r11, [rsp+88h+var_18]
0x1401bd860  mov     rbx, [r11+20h]
0x1401bd864  mov     rbp, [r11+38h]
0x1401bd868  mov     rsp, r11
0x1401bd86b  pop     r14
0x1401bd86d  pop     rdi
0x1401bd86e  pop     rsi
0x1401bd86f  retn
0x1401bd871  mov     [rdi], eax
0x1401bd873  mov     r8, rdi
0x1401bd876  mov     edx, [rbx+r14+14h]
0x1401bd87b  jmp     short loc_1401BD889
0x1401bd87d  movsxd  r8, dword ptr [rdi]
0x1401bd880  jmp     short loc_1401BD876
0x1401bd882  mov     r8, [rbx+r14+18h]; pvParam
0x1401bd887  mov     edx, [rdi]; uiParam
0x1401bd889  mov     ecx, [rbx+r14+0Ch]; uiAction
0x1401bd88e  mov     r9d, esi; fWinIni
0x1401bd891  call    cs:__imp_SystemParametersInfoW
0x1401bd898  nop     dword ptr [rax+rax+00h]
0x1401bd89d  test    eax, eax
0x1401bd89f  jnz     short loc_1401BD84C
0x1401bd8a1  call    cs:__imp_GetLastError
0x1401bd8a8  nop     dword ptr [rax+rax+00h]
0x1401bd8ad  test    eax, eax
0x1401bd8af  jle     short loc_1401BD84E
0x1401bd8b1  movzx   eax, ax
0x1401bd8b4  or      eax, 80070000h
0x1401bd8b9  jmp     short loc_1401BD84E
```
