# CLocalDevice::GetDeviceDisplayName(ulong,ushort * *)

- ea: `0x18056e870`
- end: `0x18056eb7c`
- name: `?GetDeviceDisplayName@CLocalDevice@@AEAAJKPEAPEAG@Z`
- size: `780`
- prototype: `__int64 __fastcall(CLocalDevice *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18056e860`
- `0x18056fde0`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x18003cc5c`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x18056e870`
- `0x18056f418`

## import_xrefs

- `setupapi!CM_Locate_DevNodeW` at `0x18056e9b6`
- `setupapi!CM_Locate_DevNodeW` at `0x18056e9b6`
- `OLE32!CoTaskMemFree` at `0x18056eae7`
- `OLE32!CoTaskMemFree` at `0x18056eb3b`
- `OLE32!CoTaskMemFree` at `0x18056eb49`
- `OLE32!CoTaskMemFree` at `0x18056eb52`
- `OLE32!CoTaskMemFree` at `0x18056eae7`
- `OLE32!CoTaskMemFree` at `0x18056eb3b`
- `OLE32!CoTaskMemFree` at `0x18056eb49`
- `OLE32!CoTaskMemFree` at `0x18056eb52`
- `OLE32!CoTaskMemAlloc` at `0x18056ea5d`
- `OLE32!CoTaskMemAlloc` at `0x18056eb0c`
- `OLE32!CoTaskMemAlloc` at `0x18056ea5d`
- `OLE32!CoTaskMemAlloc` at `0x18056eb0c`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x18056ea1f`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x18056ea4b`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x18056eada`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x18056ea1f`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x18056ea4b`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x18056eada`
- `CFGMGR32!CM_Get_Child` at `0x18056e9e1`
- `CFGMGR32!CM_Get_Child` at `0x18056e9e1`

## pseudocode

```c
__int64 __fastcall CLocalDevice::GetDeviceDisplayName(WCHAR **this, unsigned int a2, unsigned __int16 **a3)
{
  void *v5; // rsi
  int DeviceProperty; // r14d
  void *v7; // rdi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v9; // eax
  WCHAR *v10; // rdx
  DEVNODE v11; // r15d
  DEVINST v12; // ebx
  ULONG v13; // r15d
  CONFIGRET DevNode_Registry_PropertyW; // eax
  unsigned int v15; // eax
  void *v16; // rbx
  SIZE_T v17; // r15
  unsigned __int16 *v18; // rax
  __int64 result; // rax
  unsigned int v20; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v21; // [rsp+34h] [rbp-Ch] BYREF
  LPVOID pv; // [rsp+38h] [rbp-8h] BYREF
  ULONG pulLength; // [rsp+88h] [rbp+48h] BYREF
  DEVNODE dnDevInst; // [rsp+90h] [rbp+50h] BYREF
  DEVNODE pdnDevInst; // [rsp+98h] [rbp+58h] BYREF

  v21 = 0;
  dnDevInst = 0;
  v5 = 0;
  v20 = 0;
  pv = 0;
  pulLength = 0;
  if ( !a2 || a2 == 12 )
  {
    v7 = 0;
    DeviceProperty = CLocalDevice::GetDeviceProperty((CLocalDevice *)this, a2, &v21, (unsigned __int8 **)&pv, &v20);
    if ( DeviceProperty == -2147024883 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          WPP_714a6d298d2233154907540e19009056_Traceguids,
          CurrentThreadActivityIdPrefix,
          -2147024883);
      }
    }
    else if ( DeviceProperty >= 0 )
    {
      v10 = this[9];
      pdnDevInst = 0;
      if ( !CM_Locate_DevNodeW(&pdnDevInst, v10, 1u) )
      {
        v11 = pdnDevInst;
        if ( pdnDevInst )
        {
          v12 = pdnDevInst;
          for ( dnDevInst = 0; !CM_Get_Child(&dnDevInst, v12, 0); v12 = dnDevInst )
            ;
          dnDevInst = v12;
          if ( v12 != v11 )
          {
            v13 = 13;
            pulLength = 0;
            DevNode_Registry_PropertyW = CM_Get_DevNode_Registry_PropertyW(v12, 0xDu, 0, 0, &pulLength, 0);
            if ( DevNode_Registry_PropertyW == 37 )
            {
              pulLength = 0;
              v13 = 1;
              DevNode_Registry_PropertyW = CM_Get_DevNode_Registry_PropertyW(dnDevInst, 1u, 0, 0, &pulLength, 0);
            }
            if ( DevNode_Registry_PropertyW == 26 )
            {
              v7 = CoTaskMemAlloc(pulLength);
              if ( v7 )
              {
                if ( CM_Get_DevNode_Registry_PropertyW(dnDevInst, v13, 0, v7, &pulLength, 0) )
                {
                  CoTaskMemFree(v7);
                  v7 = 0;
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = RdpWppGetCurrentThreadActivityIdPrefix();
                  WPP_SF_Ds(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    47,
                    (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
                    v15,
                    (__int64)"BYTE");
                }
                DeviceProperty = -2147024882;
              }
            }
          }
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
           && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
        v9,
        (__int64)"GetDeviceProperty failed",
        DeviceProperty);
    }
    v16 = pv;
    if ( pv )
    {
      if ( v7 )
      {
        v17 = pulLength + 6 + v20;
        v18 = (unsigned __int16 *)CoTaskMemAlloc(v17);
        v5 = v18;
        if ( v18 )
        {
          if ( (int)StringCbPrintfW(v18, (unsigned int)v17, L"%ws (%ws)", v16, v7) >= 0 )
          {
            CoTaskMemFree(v16);
          }
          else
          {
            CoTaskMemFree(v5);
            v5 = v16;
          }
        }
        CoTaskMemFree(v7);
      }
      else
      {
        v5 = pv;
      }
    }
  }
  else
  {
    DeviceProperty = -2147024809;
  }
  result = (unsigned int)DeviceProperty;
  *a3 = (unsigned __int16 *)v5;
  return result;
}

```

## disassembly

```asm
0x18056e870  mov     [rsp-38h+arg_0], rbx
0x18056e875  push    rbp
0x18056e876  push    rsi
0x18056e877  push    rdi
0x18056e878  push    r12
0x18056e87a  push    r13
0x18056e87c  push    r14
0x18056e87e  push    r15
0x18056e880  mov     rbp, rsp
0x18056e883  sub     rsp, 40h
0x18056e887  xor     r13d, r13d
0x18056e88a  mov     r12, r8
0x18056e88d  mov     [rbp+var_C], r13d
0x18056e891  mov     rbx, rcx
0x18056e894  mov     [rbp+dnDevInst], r13d
0x18056e898  mov     esi, r13d
0x18056e89b  mov     [rbp+var_10], r13d
0x18056e89f  mov     [rbp+pv], r13
0x18056e8a3  mov     [rbp+arg_8], r13d
0x18056e8a7  test    edx, edx
0x18056e8a9  jz      short loc_18056E8BB
0x18056e8ab  cmp     edx, 0Ch
0x18056e8ae  jz      short loc_18056E8BB
0x18056e8b0  mov     r14d, 80070057h
0x18056e8b6  jmp     loc_18056EB5D
0x18056e8bb  lea     rax, [rbp+var_10]
0x18056e8bf  mov     rdi, r13
0x18056e8c2  lea     r9, [rbp+pv]; unsigned __int8 **
0x18056e8c6  mov     [rsp+40h+pulLength], rax; unsigned int *
0x18056e8cb  lea     r8, [rbp+var_C]; unsigned int *
0x18056e8cf  call    ?GetDeviceProperty@CLocalDevice@@QEAAJKPEAKPEAPEAE0@Z; CLocalDevice::GetDeviceProperty(ulong,ulong *,uchar * *,ulong *)
0x18056e8d4  mov     r14d, eax
0x18056e8d7  cmp     eax, 8007000Dh
0x18056e8dc  jnz     short loc_18056E93A
0x18056e8de  mov     rcx, cs:WPP_GLOBAL_Control
0x18056e8e5  lea     rax, WPP_GLOBAL_Control
0x18056e8ec  cmp     rcx, rax
0x18056e8ef  jz      loc_18056EAF0
0x18056e8f5  test    byte ptr [rcx+1Ch], 80h
0x18056e8f9  jz      loc_18056EAF0
0x18056e8ff  cmp     byte ptr [rcx+19h], 3
0x18056e903  jb      loc_18056EAF0
0x18056e909  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056e90e  mov     rcx, cs:WPP_GLOBAL_Control
0x18056e915  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056e91c  mov     edx, 2Dh ; '-'
0x18056e921  mov     dword ptr [rsp+40h+pulLength], 8007000Dh
0x18056e929  mov     r9d, eax
0x18056e92c  mov     rcx, [rcx+10h]
0x18056e930  call    WPP_SF_Dd
0x18056e935  jmp     loc_18056EAF0
0x18056e93a  test    r14d, r14d
0x18056e93d  jns     short loc_18056E9A4
0x18056e93f  mov     rcx, cs:WPP_GLOBAL_Control
0x18056e946  lea     rax, WPP_GLOBAL_Control
0x18056e94d  cmp     rcx, rax
0x18056e950  jz      loc_18056EAF0
0x18056e956  test    byte ptr [rcx+1Ch], 8
0x18056e95a  jz      loc_18056EAF0
0x18056e960  cmp     byte ptr [rcx+19h], 2
0x18056e964  jb      loc_18056EAF0
0x18056e96a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056e96f  lea     rcx, aGetdeviceprope_0; "GetDeviceProperty failed"
0x18056e976  mov     [rsp+40h+ulFlags], r14d
0x18056e97b  mov     [rsp+40h+pulLength], rcx
0x18056e980  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056e987  mov     rcx, cs:WPP_GLOBAL_Control
0x18056e98e  mov     edx, 2Eh ; '.'
0x18056e993  mov     r9d, eax
0x18056e996  mov     rcx, [rcx+10h]
0x18056e99a  call    WPP_SF_DsD
0x18056e99f  jmp     loc_18056EAF0
0x18056e9a4  mov     rdx, [rbx+48h]; pDeviceID
0x18056e9a8  lea     rcx, [rbp+pdnDevInst]; pdnDevInst
0x18056e9ac  mov     r8d, 1; ulFlags
0x18056e9b2  mov     [rbp+pdnDevInst], r13d
0x18056e9b6  call    cs:__imp_CM_Locate_DevNodeW
0x18056e9bc  test    eax, eax
0x18056e9be  jnz     loc_18056EAF0
0x18056e9c4  mov     r15d, [rbp+pdnDevInst]
0x18056e9c8  test    r15d, r15d
0x18056e9cb  jz      loc_18056EAF0
0x18056e9d1  mov     ebx, r15d
0x18056e9d4  mov     [rbp+dnDevInst], r13d
0x18056e9d8  xor     r8d, r8d; ulFlags
0x18056e9db  lea     rcx, [rbp+dnDevInst]; pdnDevInst
0x18056e9df  mov     edx, ebx; dnDevInst
0x18056e9e1  call    cs:__imp_CM_Get_Child
0x18056e9e7  test    eax, eax
0x18056e9e9  jnz     short loc_18056E9F0
0x18056e9eb  mov     ebx, [rbp+dnDevInst]
0x18056e9ee  jmp     short loc_18056E9D8
0x18056e9f0  mov     [rbp+dnDevInst], ebx
0x18056e9f3  cmp     ebx, r15d
0x18056e9f6  jz      loc_18056EAF0
0x18056e9fc  lea     rax, [rbp+arg_8]
0x18056ea00  mov     [rsp+40h+ulFlags], r13d; ulFlags
0x18056ea05  mov     r15d, 0Dh
0x18056ea0b  mov     [rbp+arg_8], r13d
0x18056ea0f  mov     edx, r15d; ulProperty
0x18056ea12  mov     [rsp+40h+pulLength], rax; pulLength
0x18056ea17  xor     r9d, r9d; Buffer
0x18056ea1a  xor     r8d, r8d; pulRegDataType
0x18056ea1d  mov     ecx, ebx; dnDevInst
0x18056ea1f  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x18056ea25  cmp     eax, 25h ; '%'
0x18056ea28  jnz     short loc_18056EA51
0x18056ea2a  mov     ecx, [rbp+dnDevInst]; dnDevInst
0x18056ea2d  lea     edx, [rax-24h]; ulProperty
0x18056ea30  lea     rax, [rbp+arg_8]
0x18056ea34  mov     [rsp+40h+ulFlags], r13d; ulFlags
0x18056ea39  xor     r9d, r9d; Buffer
0x18056ea3c  mov     [rsp+40h+pulLength], rax; pulLength
0x18056ea41  xor     r8d, r8d; pulRegDataType
0x18056ea44  mov     [rbp+arg_8], r13d
0x18056ea48  mov     r15d, edx
0x18056ea4b  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x18056ea51  cmp     eax, 1Ah
0x18056ea54  jnz     loc_18056EAF0
0x18056ea5a  mov     ecx, [rbp+arg_8]; cb
0x18056ea5d  call    cs:__imp_CoTaskMemAlloc
0x18056ea63  mov     rdi, rax
0x18056ea66  test    rax, rax
0x18056ea69  jnz     short loc_18056EAC0
0x18056ea6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18056ea72  lea     rax, WPP_GLOBAL_Control
0x18056ea79  cmp     rcx, rax
0x18056ea7c  jz      short loc_18056EAB8
0x18056ea7e  test    byte ptr [rcx+1Ch], 8
0x18056ea82  jz      short loc_18056EAB8
0x18056ea84  cmp     byte ptr [rcx+19h], 2
0x18056ea88  jb      short loc_18056EAB8
0x18056ea8a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056ea8f  lea     rcx, aByte_0; "BYTE"
0x18056ea96  mov     r9d, eax
0x18056ea99  mov     [rsp+40h+pulLength], rcx
0x18056ea9e  lea     edx, [rdi+2Fh]
0x18056eaa1  mov     rcx, cs:WPP_GLOBAL_Control
0x18056eaa8  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056eaaf  mov     rcx, [rcx+10h]
0x18056eab3  call    WPP_SF_Ds
0x18056eab8  mov     r14d, 8007000Eh
0x18056eabe  jmp     short loc_18056EAF0
0x18056eac0  mov     ecx, [rbp+dnDevInst]; dnDevInst
0x18056eac3  lea     rax, [rbp+arg_8]
0x18056eac7  mov     [rsp+40h+ulFlags], r13d; ulFlags
0x18056eacc  mov     r9, rdi; Buffer
0x18056eacf  xor     r8d, r8d; pulRegDataType
0x18056ead2  mov     [rsp+40h+pulLength], rax; pulLength
0x18056ead7  mov     edx, r15d; ulProperty
0x18056eada  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x18056eae0  test    eax, eax
0x18056eae2  jz      short loc_18056EAF0
0x18056eae4  mov     rcx, rdi; pv
0x18056eae7  call    cs:__imp_CoTaskMemFree
0x18056eaed  mov     rdi, r13
0x18056eaf0  mov     rbx, [rbp+pv]
0x18056eaf4  test    rbx, rbx
0x18056eaf7  jz      short loc_18056EB5D
0x18056eaf9  test    rdi, rdi
0x18056eafc  jz      short loc_18056EB5A
0x18056eafe  mov     eax, [rbp+arg_8]
0x18056eb01  mov     ecx, [rbp+var_10]
0x18056eb04  add     eax, 6
0x18056eb07  add     ecx, eax; cb
0x18056eb09  mov     r15d, ecx
0x18056eb0c  call    cs:__imp_CoTaskMemAlloc
0x18056eb12  mov     rsi, rax
0x18056eb15  test    rax, rax
0x18056eb18  jz      short loc_18056EB4F
0x18056eb1a  mov     r9, rbx
0x18056eb1d  mov     [rsp+40h+pulLength], rdi
0x18056eb22  lea     r8, aWsWs; "%ws (%ws)"
0x18056eb29  mov     edx, r15d; unsigned __int64
0x18056eb2c  mov     rcx, rax; unsigned __int16 *
0x18056eb2f  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18056eb34  test    eax, eax
0x18056eb36  jns     short loc_18056EB46
0x18056eb38  mov     rcx, rsi; pv
0x18056eb3b  call    cs:__imp_CoTaskMemFree
0x18056eb41  mov     rsi, rbx
0x18056eb44  jmp     short loc_18056EB4F
0x18056eb46  mov     rcx, rbx; pv
0x18056eb49  call    cs:__imp_CoTaskMemFree
0x18056eb4f  mov     rcx, rdi; pv
0x18056eb52  call    cs:__imp_CoTaskMemFree
0x18056eb58  jmp     short loc_18056EB5D
0x18056eb5a  mov     rsi, rbx
0x18056eb5d  mov     rbx, [rsp+40h+arg_0]
0x18056eb65  mov     eax, r14d
0x18056eb68  mov     [r12], rsi
0x18056eb6c  add     rsp, 40h
0x18056eb70  pop     r15
0x18056eb72  pop     r14
0x18056eb74  pop     r13
0x18056eb76  pop     r12
0x18056eb78  pop     rdi
0x18056eb79  pop     rsi
0x18056eb7a  pop     rbp
0x18056eb7b  retn
```
