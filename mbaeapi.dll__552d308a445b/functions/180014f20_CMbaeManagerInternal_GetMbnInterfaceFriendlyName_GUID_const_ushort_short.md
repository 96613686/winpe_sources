# CMbaeManagerInternal::GetMbnInterfaceFriendlyName(_GUID const &,ushort * *,short *)

- ea: `0x180014f20`
- end: `0x1800151bf`
- name: `?GetMbnInterfaceFriendlyName@CMbaeManagerInternal@@UEAAJAEBU_GUID@@PEAPEAGPEAF@Z`
- size: `671`
- prototype: `__int64 __fastcall(CMbaeManagerInternal *__hidden this, const struct _GUID *, unsigned __int16 **, __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800024e0`
- `0x1800143bc`
- `0x180014410`
- `0x180014f20`
- `0x1800151c8`
- `0x180015a60`
- `0x180016254`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015190`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180015182`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180015182`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001505e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180015170`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001505e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180015170`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180014fd6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180014fd6`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18001502d`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18001502d`

## pseudocode

```c
__int64 __fastcall CMbaeManagerInternal::GetMbnInterfaceFriendlyName(
        CMbaeManagerInternal *this,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        __int16 *a4)
{
  unsigned __int16 *v7; // rdi
  int v8; // eax
  CMbaeManagerInternal *v9; // rcx
  signed int v10; // ebx
  int Interface; // eax
  __int64 v12; // rdx
  int ConnectionName; // eax
  int v14; // eax
  unsigned __int16 *v15; // rax
  __int64 v16; // rcx
  __int64 v18; // [rsp+40h] [rbp-49h] BYREF
  _DWORD v19[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v20; // [rsp+50h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-31h] BYREF
  __int64 v22; // [rsp+60h] [rbp-29h]
  __int64 v23; // [rsp+68h] [rbp-21h]
  CMbaeManagerInternal *v24; // [rsp+70h] [rbp-19h]
  __int64 v25; // [rsp+78h] [rbp-11h]
  const char *v26; // [rsp+80h] [rbp-9h]
  __int64 v27; // [rsp+88h] [rbp-1h]
  const struct _GUID *v28; // [rsp+90h] [rbp+7h]
  __int64 v29; // [rsp+98h] [rbp+Fh]

  if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
  {
    v28 = a2;
    v26 = "CMbaeManagerInternal::GetMbnInterfaceFriendlyName";
    v27 = 50;
    v29 = 16;
    McGenEventWrite_EventWriteTransfer(&CtlGuid_Context, CMbaeManagerInternal_cpp457, a3, 3);
  }
  *a3 = 0;
  *a4 = 0;
  pv = 0;
  v7 = 0;
  v22 = 0;
  v23 = 0;
  v19[0] = 0;
  v18 = 0;
  v19[1] = 0;
  v20 = -1;
  v8 = WwanOpenHandle(1, 0, v19, &v20);
  v10 = v8;
  if ( v8 > 0 )
    v10 = (unsigned __int16)v8 | 0x80070000;
  if ( v10 >= 0 )
  {
    v24 = (CMbaeManagerInternal *)&v18;
    v25 = 0;
    LOBYTE(v26) = 1;
    Interface = WwanQueryInterface(v20, a2, 36);
    v10 = Interface;
    if ( Interface > 0 )
      v10 = (unsigned __int16)Interface | 0x80070000;
    if ( (_BYTE)v26 )
    {
      v9 = v24;
      v12 = *(_QWORD *)v24;
      *(_QWORD *)v24 = v25;
      if ( v12 )
        WwanFreeMemory(v12);
    }
    if ( v10 >= 0 )
    {
      if ( ((*(_DWORD *)v18 - 4) & 0xFFFFFFFD) != 0 )
      {
        v22 = -1;
        v23 = -1;
        ConnectionName = CMbaeManagerInternal::_GetConnectionName(
                           v9,
                           a2,
                           (const unsigned __int16 *)(v18 + 40),
                           (unsigned __int16 **)&pv);
        v10 = ConnectionName;
        if ( ConnectionName >= 0 )
        {
          v7 = (unsigned __int16 *)pv;
          if ( pv && *(_WORD *)pv )
          {
LABEL_23:
            if ( v10 >= 0 )
            {
              if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
                McTemplateU0sz_EventWriteTransfer(
                  v9,
                  CMbaeManagerInternal_cpp523,
                  "CMbaeManagerInternal::GetMbnInterfaceFriendlyName",
                  v7);
              v15 = v7;
              v7 = 0;
              *a3 = v15;
            }
            goto LABEL_29;
          }
        }
        else if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 2) != 0 )
        {
          McTemplateU0sd_EventWriteTransfer(
            v9,
            CMbaeManagerInternal_cpp494,
            "CMbaeManagerInternal::GetMbnInterfaceFriendlyName",
            (unsigned int)ConnectionName);
        }
      }
      v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(&pv);
      v10 = v14;
      if ( v14 >= 0 )
      {
        *a4 = -1;
      }
      else if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 2) != 0 )
      {
        McTemplateU0sd_EventWriteTransfer(
          v9,
          CMbaeManagerInternal_cpp508,
          "CMbaeManagerInternal::GetMbnInterfaceFriendlyName",
          (unsigned int)v14);
      }
      v7 = (unsigned __int16 *)pv;
      goto LABEL_23;
    }
  }
  if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 2) != 0 )
    McTemplateU0sd_EventWriteTransfer(
      v9,
      CMbaeManagerInternal_cpp518,
      "CMbaeManagerInternal::GetMbnInterfaceFriendlyName",
      (unsigned int)v10);
LABEL_29:
  if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
    McTemplateU0sd_EventWriteTransfer(
      v9,
      CMbaeManagerInternal_cpp527,
      "CMbaeManagerInternal::GetMbnInterfaceFriendlyName",
      (unsigned int)v10);
  v16 = v18;
  v18 = 0;
  if ( v16 )
    WwanFreeMemory(v16);
  if ( v20 != -1 )
    WwanCloseHandle(v20, 0);
  if ( v7 )
    CoTaskMemFree(v7);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180014f20  mov     [rsp-8+arg_0], rbx
0x180014f25  push    rbp
0x180014f26  push    rsi
0x180014f27  push    rdi
0x180014f28  push    r12
0x180014f2a  push    r13
0x180014f2c  push    r14
0x180014f2e  push    r15
0x180014f30  lea     rbp, [rsp-27h]
0x180014f35  sub     rsp, 0B0h
0x180014f3c  mov     rax, cs:__security_cookie
0x180014f43  xor     rax, rsp
0x180014f46  mov     [rbp+57h+var_40], rax
0x180014f4a  xor     r12d, r12d
0x180014f4d  lea     r13, aCmbaemanagerin_7; "CMbaeManagerInternal::GetMbnInterfaceFr"...
0x180014f54  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x180014f5b  mov     r14, r9
0x180014f5e  mov     r15, r8
0x180014f61  mov     rsi, rdx
0x180014f64  jz      short loc_180014F9F
0x180014f66  mov     [rbp+57h+var_50], rdx
0x180014f6a  lea     rax, [rbp+57h+var_70]
0x180014f6e  lea     rdx, CMbaeManagerInternal_cpp457
0x180014f75  mov     [rsp+0E0h+var_C0], rax
0x180014f7a  lea     r9d, [r12+3]
0x180014f7f  mov     [rbp+57h+var_60], r13
0x180014f83  lea     rcx, CtlGuid_Context
0x180014f8a  mov     [rbp+57h+var_58], 32h ; '2'
0x180014f92  mov     [rbp+57h+var_48], 10h
0x180014f9a  call    McGenEventWrite_EventWriteTransfer
0x180014f9f  xor     edx, edx
0x180014fa1  mov     [r15], r12
0x180014fa4  lea     r9, [rbp+57h+var_90]
0x180014fa8  mov     [r14], r12w
0x180014fac  lea     r8, [rbp+57h+var_98]
0x180014fb0  mov     [rbp+57h+pv], r12
0x180014fb4  mov     rdi, r12
0x180014fb7  mov     [rbp+57h+var_80], r12
0x180014fbb  lea     ecx, [rdx+1]
0x180014fbe  mov     [rbp+57h+var_78], r12
0x180014fc2  mov     [rbp+57h+var_98], r12d
0x180014fc6  mov     [rbp+57h+var_A0], r12
0x180014fca  mov     [rbp+57h+var_94], r12d
0x180014fce  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFFh
0x180014fd6  call    cs:__imp_WwanOpenHandle
0x180014fdc  mov     ebx, eax
0x180014fde  test    eax, eax
0x180014fe0  jle     short loc_180014FEB
0x180014fe2  movzx   ebx, ax
0x180014fe5  or      ebx, 80070000h
0x180014feb  test    ebx, ebx
0x180014fed  js      loc_18001512D
0x180014ff3  mov     rcx, [rbp+57h+var_90]
0x180014ff7  lea     rax, [rbp+57h+var_A0]
0x180014ffb  mov     [rbp+57h+var_70], rax
0x180014fff  xor     r9d, r9d
0x180015002  mov     [rsp+0E0h+var_A8], r12
0x180015007  lea     rax, [rbp+57h+var_68]
0x18001500b  mov     [rsp+0E0h+var_B0], r12
0x180015010  mov     rdx, rsi
0x180015013  mov     [rsp+0E0h+var_B8], rax
0x180015018  lea     rax, [rbp+57h+var_94]
0x18001501c  lea     r8d, [r9+24h]
0x180015020  mov     [rsp+0E0h+var_C0], rax
0x180015025  mov     [rbp+57h+var_68], r12
0x180015029  mov     byte ptr [rbp+57h+var_60], 1
0x18001502d  call    cs:__imp_WwanQueryInterface
0x180015033  mov     ebx, eax
0x180015035  test    eax, eax
0x180015037  jle     short loc_180015042
0x180015039  movzx   ebx, ax
0x18001503c  or      ebx, 80070000h
0x180015042  cmp     byte ptr [rbp+57h+var_60], r12b
0x180015046  jz      short loc_180015064
0x180015048  mov     rcx, [rbp+57h+var_70]
0x18001504c  mov     rax, [rbp+57h+var_68]
0x180015050  mov     rdx, [rcx]
0x180015053  mov     [rcx], rax
0x180015056  test    rdx, rdx
0x180015059  jz      short loc_180015064
0x18001505b  mov     rcx, rdx
0x18001505e  call    cs:__imp_WwanFreeMemory
0x180015064  test    ebx, ebx
0x180015066  js      loc_18001512D
0x18001506c  mov     r8, [rbp+57h+var_A0]
0x180015070  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180015074  mov     eax, [r8]
0x180015077  sub     eax, 4
0x18001507a  test    eax, 0FFFFFFFDh
0x18001507f  jz      short loc_1800150CF
0x180015081  add     r8, 28h ; '('; unsigned __int16 *
0x180015085  mov     [rbp+57h+var_80], rdi
0x180015089  lea     r9, [rbp+57h+pv]; unsigned __int16 **
0x18001508d  mov     [rbp+57h+var_78], rdi
0x180015091  mov     rdx, rsi; struct _GUID *
0x180015094  call    ?_GetConnectionName@CMbaeManagerInternal@@AEAAJAEBU_GUID@@PEBGPEAPEAG@Z; CMbaeManagerInternal::_GetConnectionName(_GUID const &,ushort const *,ushort * *)
0x180015099  mov     ebx, eax
0x18001509b  test    eax, eax
0x18001509d  jns     short loc_1800150BC
0x18001509f  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 2
0x1800150a6  jz      short loc_1800150CF
0x1800150a8  mov     r9d, eax
0x1800150ab  lea     rdx, CMbaeManagerInternal_cpp494
0x1800150b2  mov     r8, r13
0x1800150b5  call    McTemplateU0sd_EventWriteTransfer
0x1800150ba  jmp     short loc_1800150CF
0x1800150bc  mov     rdi, [rbp+57h+pv]
0x1800150c0  test    rdi, rdi
0x1800150c3  jz      short loc_1800150CB
0x1800150c5  cmp     [rdi], r12w
0x1800150c9  jnz     short loc_180015103
0x1800150cb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800150cf  lea     rcx, [rbp+57h+pv]
0x1800150d3  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@I@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint)
0x1800150d8  mov     ebx, eax
0x1800150da  test    eax, eax
0x1800150dc  jns     short loc_1800150FB
0x1800150de  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 2
0x1800150e5  jz      short loc_1800150FF
0x1800150e7  mov     r9d, eax
0x1800150ea  lea     rdx, CMbaeManagerInternal_cpp508
0x1800150f1  mov     r8, r13
0x1800150f4  call    McTemplateU0sd_EventWriteTransfer
0x1800150f9  jmp     short loc_1800150FF
0x1800150fb  mov     [r14], di
0x1800150ff  mov     rdi, [rbp+57h+pv]
0x180015103  test    ebx, ebx
0x180015105  js      short loc_180015148
0x180015107  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x18001510e  jz      short loc_180015122
0x180015110  mov     r9, rdi
0x180015113  lea     rdx, CMbaeManagerInternal_cpp523
0x18001511a  mov     r8, r13
0x18001511d  call    McTemplateU0sz_EventWriteTransfer
0x180015122  mov     rax, rdi
0x180015125  mov     rdi, r12
0x180015128  mov     [r15], rax
0x18001512b  jmp     short loc_180015148
0x18001512d  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 2
0x180015134  jz      short loc_180015148
0x180015136  mov     r9d, ebx
0x180015139  lea     rdx, CMbaeManagerInternal_cpp518
0x180015140  mov     r8, r13
0x180015143  call    McTemplateU0sd_EventWriteTransfer
0x180015148  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x18001514f  jz      short loc_180015163
0x180015151  mov     r9d, ebx
0x180015154  lea     rdx, CMbaeManagerInternal_cpp527
0x18001515b  mov     r8, r13
0x18001515e  call    McTemplateU0sd_EventWriteTransfer
0x180015163  mov     rcx, [rbp+57h+var_A0]
0x180015167  mov     [rbp+57h+var_A0], r12
0x18001516b  test    rcx, rcx
0x18001516e  jz      short loc_180015176
0x180015170  call    cs:__imp_WwanFreeMemory
0x180015176  mov     rcx, [rbp+57h+var_90]
0x18001517a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001517e  jz      short loc_180015188
0x180015180  xor     edx, edx
0x180015182  call    cs:__imp_WwanCloseHandle
0x180015188  test    rdi, rdi
0x18001518b  jz      short loc_180015196
0x18001518d  mov     rcx, rdi; pv
0x180015190  call    cs:__imp_CoTaskMemFree
0x180015196  mov     eax, ebx
0x180015198  mov     rcx, [rbp+57h+var_40]
0x18001519c  xor     rcx, rsp; StackCookie
0x18001519f  call    __security_check_cookie
0x1800151a4  mov     rbx, [rsp+0E0h+arg_0]
0x1800151ac  add     rsp, 0B0h
0x1800151b3  pop     r15
0x1800151b5  pop     r14
0x1800151b7  pop     r13
0x1800151b9  pop     r12
0x1800151bb  pop     rdi
0x1800151bc  pop     rsi
0x1800151bd  pop     rbp
0x1800151be  retn
```
