# SystemSettings::TurnOn(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)

- ea: `0x140021f84`
- end: `0x140022130`
- name: `?TurnOn@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140020938`

## callees

- `0x140021c20`
- `0x140021db4`
- `0x140021f84`
- `0x140025d42`
- `0x140025d70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002211c`
- `KERNEL32!GetLastError` at `0x14002211c`
- `USER32!SystemParametersInfoW` at `0x140022068`
- `USER32!SystemParametersInfoW` at `0x1400220ae`
- `USER32!SystemParametersInfoW` at `0x140022112`
- `USER32!SystemParametersInfoW` at `0x140022068`
- `USER32!SystemParametersInfoW` at `0x1400220ae`
- `USER32!SystemParametersInfoW` at `0x140022112`
- `USER32!SendNotifyMessageW` at `0x1400220c8`
- `USER32!SendNotifyMessageW` at `0x1400220c8`

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
0x140021f84  mov     [rsp+arg_0], rbx
0x140021f89  mov     [rsp+arg_18], rbp
0x140021f8e  push    rsi
0x140021f8f  push    rdi
0x140021f90  push    r14
0x140021f92  sub     rsp, 70h
0x140021f96  mov     rax, cs:__security_cookie
0x140021f9d  xor     rax, rsp
0x140021fa0  mov     [rsp+88h+var_28], rax
0x140021fa5  mov     eax, r9d
0x140021fa8  mov     ebx, edx
0x140021faa  neg     eax
0x140021fac  lea     r14, ?_systemSetting@SystemSettings@@0PAUSystemSetting@@A; SystemSetting near * SystemSettings::_systemSetting
0x140021fb3  mov     rdi, r8
0x140021fb6  mov     ebp, r9d
0x140021fb9  mov     r8, [rcx]
0x140021fbc  sbb     esi, esi
0x140021fbe  shl     rbx, 5
0x140021fc2  and     esi, 3
0x140021fc5  mov     rax, [rbx+r14]
0x140021fc9  sub     r8, rax
0x140021fcc  movzx   edx, word ptr [rax]
0x140021fcf  movzx   ecx, word ptr [rax+r8]
0x140021fd4  sub     edx, ecx
0x140021fd6  jnz     short loc_140021FE0
0x140021fd8  add     rax, 2
0x140021fdc  test    ecx, ecx
0x140021fde  jnz     short loc_140021FCC
0x140021fe0  test    edx, edx
0x140021fe2  jz      short loc_140021FEE
0x140021fe4  mov     eax, 80070057h
0x140021fe9  jmp     loc_1400220D0
0x140021fee  mov     rcx, [rbx+r14]; String1
0x140021ff2  lea     rdx, aAnimations; "animations"
0x140021ff9  call    wcscmp_0
0x140021ffe  test    eax, eax
0x140022000  jnz     short loc_140022011
0x140022002  mov     ecx, [rdi]; pvParam
0x140022004  call    ?SetAdditionalAnimationSetting@SystemSettings@@CAJI@Z; SystemSettings::SetAdditionalAnimationSetting(uint)
0x140022009  test    eax, eax
0x14002200b  js      loc_1400220D0
0x140022011  mov     ecx, [rbx+r14+10h]
0x140022016  test    ecx, ecx
0x140022018  jz      loc_140022103
0x14002201e  sub     ecx, 1
0x140022021  jz      loc_1400220FE
0x140022027  cmp     ecx, 1
0x14002202a  jnz     loc_1400220CE
0x140022030  mov     eax, [rbx+r14+14h]
0x140022035  test    rdi, rdi
0x140022038  jnz     loc_1400220F2
0x14002203e  mov     ecx, [rbx+r14+8]; uiAction
0x140022043  lea     r8, [rsp+88h+pvParam]; pvParam
0x140022048  xorps   xmm0, xmm0
0x14002204b  xor     r9d, r9d; fWinIni
0x14002204e  movups  [rsp+88h+pvParam], xmm0
0x140022053  mov     edx, eax; uiParam
0x140022055  mov     dword ptr [rsp+88h+pvParam], eax
0x140022059  movups  xmmword ptr [rsp+88h+var_48], xmm0
0x14002205e  movups  xmmword ptr [rsp+88h+var_48+0Ch], xmm0
0x140022063  movups  [rsp+88h+var_58], xmm0
0x140022068  call    cs:__imp_SystemParametersInfoW
0x14002206e  test    eax, eax
0x140022070  jz      loc_14002211C
0x140022076  mov     eax, dword ptr [rsp+88h+pvParam+4]
0x14002207a  test    al, 1
0x14002207c  jnz     short loc_1400220CE
0x14002207e  or      eax, 1
0x140022081  cmp     dword ptr [rbx+r14+0Ch], 43h ; 'C'
0x140022087  mov     dword ptr [rsp+88h+pvParam+4], eax
0x14002208b  jnz     short loc_14002209C
0x14002208d  call    ?IsInMachineOOBEOrLogonUI@@YA_NXZ; IsInMachineOOBEOrLogonUI(void)
0x140022092  test    al, al
0x140022094  jz      short loc_14002209C
0x140022096  bts     dword ptr [rsp+88h+pvParam+4], 0Ch
0x14002209c  mov     edx, [rbx+r14+14h]; uiParam
0x1400220a1  lea     r8, [rsp+88h+pvParam]; pvParam
0x1400220a6  mov     ecx, [rbx+r14+0Ch]; uiAction
0x1400220ab  mov     r9d, esi; fWinIni
0x1400220ae  call    cs:__imp_SystemParametersInfoW
0x1400220b4  test    ebp, ebp
0x1400220b6  jnz     short loc_1400220CE
0x1400220b8  mov     r8d, [rbx+r14+0Ch]; wParam
0x1400220bd  lea     edx, [rbp+1Ah]; Msg
0x1400220c0  xor     r9d, r9d; lParam
0x1400220c3  mov     ecx, 0FFFFh; hWnd
0x1400220c8  call    cs:__imp_SendNotifyMessageW
0x1400220ce  xor     eax, eax
0x1400220d0  mov     rcx, [rsp+88h+var_28]
0x1400220d5  xor     rcx, rsp; StackCookie
0x1400220d8  call    __security_check_cookie
0x1400220dd  lea     r11, [rsp+88h+var_18]
0x1400220e2  mov     rbx, [r11+20h]
0x1400220e6  mov     rbp, [r11+38h]
0x1400220ea  mov     rsp, r11
0x1400220ed  pop     r14
0x1400220ef  pop     rdi
0x1400220f0  pop     rsi
0x1400220f1  retn
0x1400220f2  mov     [rdi], eax
0x1400220f4  mov     r8, rdi
0x1400220f7  mov     edx, [rbx+r14+14h]
0x1400220fc  jmp     short loc_14002210A
0x1400220fe  movsxd  r8, dword ptr [rdi]
0x140022101  jmp     short loc_1400220F7
0x140022103  mov     r8, [rbx+r14+18h]; pvParam
0x140022108  mov     edx, [rdi]; uiParam
0x14002210a  mov     ecx, [rbx+r14+0Ch]; uiAction
0x14002210f  mov     r9d, esi; fWinIni
0x140022112  call    cs:__imp_SystemParametersInfoW
0x140022118  test    eax, eax
0x14002211a  jnz     short loc_1400220CE
0x14002211c  call    cs:__imp_GetLastError
0x140022122  test    eax, eax
0x140022124  jle     short loc_1400220D0
0x140022126  movzx   eax, ax
0x140022129  or      eax, 80070000h
0x14002212e  jmp     short loc_1400220D0
```
