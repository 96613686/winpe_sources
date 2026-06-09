# CDeviceSettingsDialog::SaveRMInfo(ulong,ushort const *,uchar *,ulong)

- ea: `0x180011f58`
- end: `0x180012057`
- name: `?SaveRMInfo@CDeviceSettingsDialog@@AEBAKKPEBGPEAEK@Z`
- size: `255`
- prototype: `unsigned int(CDeviceSettingsDialog *__hidden this, unsigned int, const unsigned __int16 *, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180011cb0`
- `0x180012060`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x180011f58`
- `0x1800152d8`

## import_xrefs

- `FXSAPI!FaxSetExtensionDataW` at `0x180011fbc`
- `FXSAPI!FaxSetExtensionDataW` at `0x180011fbc`
- `KERNEL32!GetLastError` at `0x180011fc6`
- `KERNEL32!GetLastError` at `0x18001200d`
- `KERNEL32!GetLastError` at `0x180011fc6`
- `KERNEL32!GetLastError` at `0x18001200d`

## pseudocode

```c
__int64 __fastcall CDeviceSettingsDialog::SaveRMInfo(
        HANDLE *this,
        DWORD a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4)
{
  DWORD LastError; // eax
  DWORD v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  if ( (unsigned int)FaxSetExtensionDataW(this[7], a2, a3, a4 + 4, 520) )
  {
    v9 = 0;
    if ( !(unsigned int)FaxDeviceEnableRoutingMethod(this[7], a2, a3, *(_DWORD *)a4 != 0) )
    {
      LastError = GetLastError();
      v9 = LastError;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 60;
        goto LABEL_15;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 59;
LABEL_15:
      WPP_SF_d(v10[2], v11, &WPP_f5b496eade1b3798203481970613ce29_Traceguids, LastError);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180011f58  push    rbx
0x180011f5a  push    rbp
0x180011f5b  push    rsi
0x180011f5c  push    rdi
0x180011f5d  push    r12
0x180011f5f  push    r14
0x180011f61  sub     rsp, 38h
0x180011f65  mov     rdi, r9
0x180011f68  mov     rsi, r8
0x180011f6b  mov     ebp, edx
0x180011f6d  mov     r14, rcx
0x180011f70  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f77  lea     r12, WPP_GLOBAL_Control
0x180011f7e  cmp     rcx, r12
0x180011f81  jz      short loc_180011FA7
0x180011f83  test    dword ptr [rcx+1Ch], 100h
0x180011f8a  jz      short loc_180011FA7
0x180011f8c  cmp     byte ptr [rcx+19h], 5
0x180011f90  jb      short loc_180011FA7
0x180011f92  mov     rcx, [rcx+10h]
0x180011f96  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180011f9d  mov     edx, 3Ah ; ':'
0x180011fa2  call    WPP_SF_
0x180011fa7  mov     rcx, [r14+38h]
0x180011fab  lea     r9, [rdi+4]
0x180011faf  mov     r8, rsi
0x180011fb2  mov     [rsp+68h+var_48], 208h
0x180011fba  mov     edx, ebp
0x180011fbc  call    cs:__imp_FaxSetExtensionDataW
0x180011fc2  test    eax, eax
0x180011fc4  jnz     short loc_180011FF0
0x180011fc6  call    cs:__imp_GetLastError
0x180011fcc  mov     ebx, eax
0x180011fce  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fd5  cmp     rcx, r12
0x180011fd8  jz      short loc_180012048
0x180011fda  test    dword ptr [rcx+1Ch], 100h
0x180011fe1  jz      short loc_180012048
0x180011fe3  cmp     byte ptr [rcx+19h], 2
0x180011fe7  jb      short loc_180012048
0x180011fe9  mov     edx, 3Bh ; ';'
0x180011fee  jmp     short loc_180012035
0x180011ff0  mov     rcx, [r14+38h]; FaxHandle
0x180011ff4  xor     r9d, r9d
0x180011ff7  xor     ebx, ebx
0x180011ff9  mov     r8, rsi; RoutingGuid
0x180011ffc  cmp     [rdi], ebx
0x180011ffe  mov     edx, ebp; DeviceId
0x180012000  setnz   r9b
0x180012004  call    FaxDeviceEnableRoutingMethod
0x180012009  test    eax, eax
0x18001200b  jnz     short loc_180012048
0x18001200d  call    cs:__imp_GetLastError
0x180012013  mov     ebx, eax
0x180012015  mov     rcx, cs:WPP_GLOBAL_Control
0x18001201c  cmp     rcx, r12
0x18001201f  jz      short loc_180012048
0x180012021  test    dword ptr [rcx+1Ch], 100h
0x180012028  jz      short loc_180012048
0x18001202a  cmp     byte ptr [rcx+19h], 2
0x18001202e  jb      short loc_180012048
0x180012030  mov     edx, 3Ch ; '<'
0x180012035  mov     rcx, [rcx+10h]
0x180012039  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180012040  mov     r9d, eax
0x180012043  call    WPP_SF_d
0x180012048  mov     eax, ebx
0x18001204a  add     rsp, 38h
0x18001204e  pop     r14
0x180012050  pop     r12
0x180012052  pop     rdi
0x180012053  pop     rsi
0x180012054  pop     rbp
0x180012055  pop     rbx
0x180012056  retn
```
