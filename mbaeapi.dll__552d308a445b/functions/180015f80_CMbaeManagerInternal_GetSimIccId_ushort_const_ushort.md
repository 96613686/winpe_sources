# CMbaeManagerInternal::_GetSimIccId(ushort const *,ushort * *)

- ea: `0x180015f80`
- end: `0x18001612e`
- name: `?_GetSimIccId@CMbaeManagerInternal@@AEAAJPEBGPEAPEAG@Z`
- size: `430`
- prototype: `__int64 __fastcall(CMbaeManagerInternal *this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016164`

## callees

- `0x1800024e0`
- `0x180014410`
- `0x180015f80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016000`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015feb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015feb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800160bc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800160bc`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180015fd1`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180015fd1`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180015ff8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180016107`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180015ff8`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180016107`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800160aa`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800160f5`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800160aa`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x1800160f5`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18001601b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18001601b`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180016080`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180016080`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMbaeManagerInternal::_GetSimIccId(
        CMbaeManagerInternal *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 v4; // rcx
  int v5; // ebx
  int v6; // eax
  int v7; // eax
  __int64 v8; // rcx
  __int64 v10; // [rsp+40h] [rbp-9h] BYREF
  __int64 v11; // [rsp+48h] [rbp-1h] BYREF
  _DWORD v12[2]; // [rsp+50h] [rbp+7h] BYREF
  __int64 *v13; // [rsp+58h] [rbp+Fh]
  __int64 v14; // [rsp+60h] [rbp+17h]
  char v15; // [rsp+68h] [rbp+1Fh]
  GUID iid; // [rsp+70h] [rbp+27h] BYREF

  v10 = -1;
  v12[0] = 0;
  v11 = 0;
  iid = 0;
  v12[1] = 0;
  v5 = IIDFromString(a2, &iid);
  if ( v5 >= 0 )
  {
    v10 = -1;
    v6 = WwanOpenHandle(1, 0, v12, &v10);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v5 >= 0 )
    {
      v13 = &v11;
      v14 = 0;
      v15 = 1;
      v7 = WwanQueryInterface(v10, &iid, 36);
      v5 = v7;
      if ( v7 > 0 )
        v5 = (unsigned __int16)v7 | 0x80070000;
      if ( v15 )
      {
        v4 = *v13;
        *v13 = v14;
        if ( v4 )
          WwanFreeMemory(v4);
      }
      if ( v5 >= 0 )
        *a3 = SysAllocString((const OLECHAR *)(v11 + 40));
    }
  }
  if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
    McTemplateU0sd_EventWriteTransfer(
      v4,
      CMbaeManagerInternal_cpp187,
      "CMbaeManagerInternal::_GetSimIccId",
      (unsigned int)v5);
  v8 = v11;
  v11 = 0;
  if ( v8 )
    WwanFreeMemory(v8);
  if ( v10 != -1 )
    WwanCloseHandle(v10, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180015f80  mov     [rsp-8+arg_0], rbx
0x180015f85  push    rbp
0x180015f86  push    rsi
0x180015f87  push    rdi
0x180015f88  lea     rbp, [rsp-47h]
0x180015f8d  sub     rsp, 90h
0x180015f94  mov     rax, cs:__security_cookie
0x180015f9b  xor     rax, rsp
0x180015f9e  mov     [rbp+57h+var_20], rax
0x180015fa2  mov     rcx, rdx; lpsz
0x180015fa5  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFFh
0x180015fad  xorps   xmm0, xmm0
0x180015fb0  mov     [rbp+57h+var_50], 0
0x180015fb7  lea     rdx, [rbp+57h+iid]; lpiid
0x180015fbb  mov     [rbp+57h+var_58], 0
0x180015fc3  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x180015fc7  mov     rsi, r8
0x180015fca  mov     [rbp+57h+var_4C], 0
0x180015fd1  call    cs:__imp_IIDFromString
0x180015fd7  mov     ebx, eax
0x180015fd9  test    eax, eax
0x180015fdb  js      loc_1800160C5
0x180015fe1  mov     rdi, [rbp+57h+var_60]
0x180015fe5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180015fe9  jz      short loc_180016006
0x180015feb  call    cs:__imp_GetLastError
0x180015ff1  xor     edx, edx
0x180015ff3  mov     rcx, rdi
0x180015ff6  mov     ebx, eax
0x180015ff8  call    cs:__imp_WwanCloseHandle
0x180015ffe  mov     ecx, ebx; dwErrCode
0x180016000  call    cs:__imp_SetLastError
0x180016006  xor     edx, edx
0x180016008  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFFh
0x180016010  lea     r9, [rbp+57h+var_60]
0x180016014  lea     r8, [rbp+57h+var_50]
0x180016018  lea     ecx, [rdx+1]
0x18001601b  call    cs:__imp_WwanOpenHandle
0x180016021  mov     ebx, eax
0x180016023  mov     edi, 80070000h
0x180016028  test    eax, eax
0x18001602a  jle     short loc_180016031
0x18001602c  movzx   ebx, ax
0x18001602f  or      ebx, edi
0x180016031  test    ebx, ebx
0x180016033  js      loc_1800160C5
0x180016039  mov     rcx, [rbp+57h+var_60]
0x18001603d  lea     rax, [rbp+57h+var_58]
0x180016041  mov     [rbp+57h+var_48], rax
0x180016045  lea     rdx, [rbp+57h+iid]
0x180016049  mov     [rsp+0A0h+var_68], 0
0x180016052  lea     rax, [rbp+57h+var_40]
0x180016056  xor     r9d, r9d
0x180016059  mov     [rsp+0A0h+var_70], 0
0x180016062  mov     [rsp+0A0h+var_78], rax
0x180016067  lea     rax, [rbp+57h+var_4C]
0x18001606b  mov     [rsp+0A0h+var_80], rax
0x180016070  mov     [rbp+57h+var_40], 0
0x180016078  lea     r8d, [r9+24h]
0x18001607c  mov     [rbp+57h+var_38], 1
0x180016080  call    cs:__imp_WwanQueryInterface
0x180016086  mov     ebx, eax
0x180016088  test    eax, eax
0x18001608a  jle     short loc_180016091
0x18001608c  movzx   ebx, ax
0x18001608f  or      ebx, edi
0x180016091  cmp     [rbp+57h+var_38], 0
0x180016095  jz      short loc_1800160B0
0x180016097  mov     rdx, [rbp+57h+var_48]
0x18001609b  mov     rax, [rbp+57h+var_40]
0x18001609f  mov     rcx, [rdx]
0x1800160a2  mov     [rdx], rax
0x1800160a5  test    rcx, rcx
0x1800160a8  jz      short loc_1800160B0
0x1800160aa  call    cs:__imp_WwanFreeMemory
0x1800160b0  test    ebx, ebx
0x1800160b2  js      short loc_1800160C5
0x1800160b4  mov     rcx, [rbp+57h+var_58]
0x1800160b8  add     rcx, 28h ; '('; psz
0x1800160bc  call    cs:__imp_SysAllocString
0x1800160c2  mov     [rsi], rax
0x1800160c5  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x1800160cc  jz      short loc_1800160E4
0x1800160ce  mov     r9d, ebx
0x1800160d1  lea     r8, aCmbaemanagerin_8; "CMbaeManagerInternal::_GetSimIccId"
0x1800160d8  lea     rdx, CMbaeManagerInternal_cpp187
0x1800160df  call    McTemplateU0sd_EventWriteTransfer
0x1800160e4  mov     rcx, [rbp+57h+var_58]
0x1800160e8  mov     [rbp+57h+var_58], 0
0x1800160f0  test    rcx, rcx
0x1800160f3  jz      short loc_1800160FB
0x1800160f5  call    cs:__imp_WwanFreeMemory
0x1800160fb  mov     rcx, [rbp+57h+var_60]
0x1800160ff  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180016103  jz      short loc_18001610D
0x180016105  xor     edx, edx
0x180016107  call    cs:__imp_WwanCloseHandle
0x18001610d  mov     eax, ebx
0x18001610f  mov     rcx, [rbp+57h+var_20]
0x180016113  xor     rcx, rsp; StackCookie
0x180016116  call    __security_check_cookie
0x18001611b  mov     rbx, [rsp+0A0h+arg_0]
0x180016123  add     rsp, 90h
0x18001612a  pop     rdi
0x18001612b  pop     rsi
0x18001612c  pop     rbp
0x18001612d  retn
```
