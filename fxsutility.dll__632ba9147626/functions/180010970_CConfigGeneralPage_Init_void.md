# CConfigGeneralPage::Init(void *)

- ea: `0x180010970`
- end: `0x180010a7d`
- name: `?Init@CConfigGeneralPage@@QEAAKPEAX@Z`
- size: `269`
- prototype: `unsigned int __fastcall(CConfigGeneralPage *__hidden this, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000fd8c`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x1800108bc`
- `0x180010970`
- `0x1800124a4`

## import_xrefs

- `FXSAPI!FaxAccessCheckEx2` at `0x1800109cf`
- `FXSAPI!FaxAccessCheckEx2` at `0x1800109cf`
- `KERNEL32!GetLastError` at `0x1800109d9`
- `KERNEL32!GetLastError` at `0x1800109d9`

## pseudocode

```c
__int64 __fastcall CConfigGeneralPage::Init(CConfigGeneralPage *this, void *a2)
{
  DWORD DeviceList; // eax
  DWORD v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  *((_QWORD *)this + 15) = a2;
  *((_DWORD *)this + 32) = 1;
  if ( (unsigned int)FaxAccessCheckEx2(a2, 64, 0) )
  {
LABEL_8:
    DeviceList = CConfigGeneralPage::GetDeviceList(this);
    v5 = DeviceList;
    if ( DeviceList )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 19;
LABEL_22:
        WPP_SF_d(v6[2], v7, &WPP_f5b496eade1b3798203481970613ce29_Traceguids, DeviceList);
        return v5;
      }
    }
    else
    {
      DeviceList = CConfigGeneralPage::SetActiveDevice(this);
      v5 = DeviceList;
      if ( DeviceList )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = 20;
          goto LABEL_22;
        }
      }
    }
    return v5;
  }
  DeviceList = GetLastError();
  v5 = DeviceList;
  if ( !DeviceList )
  {
    *((_DWORD *)this + 32) = 0;
    goto LABEL_8;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 18;
    goto LABEL_22;
  }
  return v5;
}

```

## disassembly

```asm
0x180010970  push    rbx
0x180010972  push    rbp
0x180010973  push    rsi
0x180010974  push    rdi
0x180010975  sub     rsp, 28h
0x180010979  mov     rbx, rdx
0x18001097c  mov     rdi, rcx
0x18001097f  mov     rcx, cs:WPP_GLOBAL_Control
0x180010986  lea     rbp, WPP_GLOBAL_Control
0x18001098d  mov     esi, 100h
0x180010992  cmp     rcx, rbp
0x180010995  jz      short loc_1800109B7
0x180010997  test    [rcx+1Ch], esi
0x18001099a  jz      short loc_1800109B7
0x18001099c  cmp     byte ptr [rcx+19h], 5
0x1800109a0  jb      short loc_1800109B7
0x1800109a2  mov     rcx, [rcx+10h]
0x1800109a6  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x1800109ad  mov     edx, 11h
0x1800109b2  call    WPP_SF_
0x1800109b7  xor     r8d, r8d
0x1800109ba  mov     [rdi+78h], rbx
0x1800109be  mov     rcx, rbx
0x1800109c1  mov     dword ptr [rdi+80h], 1
0x1800109cb  lea     edx, [r8+40h]
0x1800109cf  call    cs:__imp_FaxAccessCheckEx2
0x1800109d5  test    eax, eax
0x1800109d7  jnz     short loc_1800109EB
0x1800109d9  call    cs:__imp_GetLastError
0x1800109df  mov     ebx, eax
0x1800109e1  test    eax, eax
0x1800109e3  jnz     short loc_180010A17
0x1800109e5  mov     [rdi+80h], eax
0x1800109eb  mov     rcx, rdi; this
0x1800109ee  call    ?GetDeviceList@CConfigGeneralPage@@AEAAKXZ; CConfigGeneralPage::GetDeviceList(void)
0x1800109f3  mov     ebx, eax
0x1800109f5  test    eax, eax
0x1800109f7  jz      short loc_180010A35
0x1800109f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a00  cmp     rcx, rbp
0x180010a03  jz      short loc_180010A72
0x180010a05  test    [rcx+1Ch], esi
0x180010a08  jz      short loc_180010A72
0x180010a0a  cmp     byte ptr [rcx+19h], 2
0x180010a0e  jb      short loc_180010A72
0x180010a10  mov     edx, 13h
0x180010a15  jmp     short loc_180010A5F
0x180010a17  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a1e  cmp     rcx, rbp
0x180010a21  jz      short loc_180010A72
0x180010a23  test    [rcx+1Ch], esi
0x180010a26  jz      short loc_180010A72
0x180010a28  cmp     byte ptr [rcx+19h], 2
0x180010a2c  jb      short loc_180010A72
0x180010a2e  mov     edx, 12h
0x180010a33  jmp     short loc_180010A5F
0x180010a35  mov     rcx, rdi; this
0x180010a38  call    ?SetActiveDevice@CConfigGeneralPage@@AEAAKXZ; CConfigGeneralPage::SetActiveDevice(void)
0x180010a3d  mov     ebx, eax
0x180010a3f  test    eax, eax
0x180010a41  jz      short loc_180010A72
0x180010a43  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a4a  cmp     rcx, rbp
0x180010a4d  jz      short loc_180010A72
0x180010a4f  test    [rcx+1Ch], esi
0x180010a52  jz      short loc_180010A72
0x180010a54  cmp     byte ptr [rcx+19h], 2
0x180010a58  jb      short loc_180010A72
0x180010a5a  mov     edx, 14h
0x180010a5f  mov     rcx, [rcx+10h]
0x180010a63  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180010a6a  mov     r9d, eax
0x180010a6d  call    WPP_SF_d
0x180010a72  mov     eax, ebx
0x180010a74  add     rsp, 28h
0x180010a78  pop     rdi
0x180010a79  pop     rsi
0x180010a7a  pop     rbp
0x180010a7b  pop     rbx
0x180010a7c  retn
```
