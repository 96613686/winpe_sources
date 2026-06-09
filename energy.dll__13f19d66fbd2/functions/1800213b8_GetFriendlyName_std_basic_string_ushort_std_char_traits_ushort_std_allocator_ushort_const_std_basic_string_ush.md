# GetFriendlyName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800213b8`
- end: `0x1800214f7`
- name: `?GetFriendlyName@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z`
- size: `319`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180021080`
- `0x180022714`
- `0x18002b03c`
- `0x180038fdc`

## callees

- `0x1800213b8`
- `0x180021500`
- `0x1800253e0`
- `0x18004ca90`
- `0x18004dea8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021492`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021492`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800214a1`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800214a1`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x180021454`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x180021454`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180021406`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180021406`

## pseudocode

```c
__int64 __fastcall GetFriendlyName(_QWORD *a1, __int64 a2)
{
  unsigned __int8 *v4; // rdi
  void *DeviceInfoList; // rsi
  bool v6; // cc
  unsigned int v7; // r8d
  unsigned __int8 *DeviceProperty; // rax
  __int64 v9; // r8
  DWORD LastError; // ebx
  __int128 v12; // [rsp+30h] [rbp-58h] BYREF
  __int128 v13; // [rsp+40h] [rbp-48h]
  __int128 v14; // [rsp+50h] [rbp-38h]

  v4 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  DeviceInfoList = (void *)DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList != (void *)-1LL )
  {
    v6 = a1[3] <= 7u;
    v12 = 0;
    LODWORD(v12) = 48;
    v13 = 0;
    v14 = 0;
    if ( !v6 )
      a1 = (_QWORD *)*a1;
    if ( (unsigned int)DevObjOpenDeviceInfo(DeviceInfoList, a1, 0, 0, &v12) )
    {
      DeviceProperty = GetDeviceProperty(DeviceInfoList, (struct _DO_DEVINFO_DATA *)&v12, v7);
      v4 = DeviceProperty;
      if ( DeviceProperty )
      {
        v9 = -1;
        do
          ++v9;
        while ( *(_WORD *)&DeviceProperty[2 * v9] );
        std::wstring::_Assign<unsigned short>(a2, DeviceProperty, v9);
        LastError = 0;
LABEL_9:
        LocalFree(v4);
        goto LABEL_10;
      }
    }
  }
  LastError = GetLastError();
  if ( LastError )
    std::wstring::assign(a2, &qword_18009CA18);
  if ( v4 )
    goto LABEL_9;
LABEL_10:
  if ( DeviceInfoList != (void *)-1LL )
    DevObjDestroyDeviceInfoList(DeviceInfoList);
  return LastError;
}

```

## disassembly

```asm
0x1800213b8  mov     [rsp+arg_10], rbx
0x1800213bd  mov     [rsp+arg_18], rbp
0x1800213c2  push    rsi
0x1800213c3  push    rdi
0x1800213c4  push    r14
0x1800213c6  sub     rsp, 70h
0x1800213ca  mov     rax, cs:__security_cookie
0x1800213d1  xor     rax, rsp
0x1800213d4  mov     [rsp+88h+var_28], rax
0x1800213d9  xorps   xmm0, xmm0
0x1800213dc  mov     rbp, rdx
0x1800213df  mov     rbx, rcx
0x1800213e2  xor     r14d, r14d
0x1800213e5  xor     edx, edx
0x1800213e7  mov     [rsp+88h+var_68], r14
0x1800213ec  xor     ecx, ecx
0x1800213ee  xor     r9d, r9d
0x1800213f1  xor     r8d, r8d
0x1800213f4  mov     edi, r14d
0x1800213f7  movups  [rsp+88h+var_58], xmm0
0x1800213fc  movups  [rsp+88h+var_48], xmm0
0x180021401  movups  [rsp+88h+var_38], xmm0
0x180021406  call    cs:__imp_DevObjCreateDeviceInfoList
0x18002140c  mov     rsi, rax
0x18002140f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021413  jz      loc_1800214D3
0x180021419  cmp     qword ptr [rbx+18h], 7
0x18002141e  xorps   xmm0, xmm0
0x180021421  movups  [rsp+88h+var_58], xmm0
0x180021426  mov     dword ptr [rsp+88h+var_58], 30h ; '0'
0x18002142e  movups  [rsp+88h+var_48], xmm0
0x180021433  movups  [rsp+88h+var_38], xmm0
0x180021438  ja      loc_1800214CB
0x18002143e  lea     rax, [rsp+88h+var_58]
0x180021443  xor     r9d, r9d
0x180021446  xor     r8d, r8d
0x180021449  mov     [rsp+88h+var_68], rax
0x18002144e  mov     rdx, rbx
0x180021451  mov     rcx, rsi
0x180021454  call    cs:__imp_DevObjOpenDeviceInfo
0x18002145a  test    eax, eax
0x18002145c  jz      short loc_1800214D3
0x18002145e  lea     rdx, [rsp+88h+var_58]; struct _DO_DEVINFO_DATA *
0x180021463  mov     rcx, rsi; void *
0x180021466  call    ?GetDeviceProperty@@YAPEAEPEAXPEAU_DO_DEVINFO_DATA@@K@Z; GetDeviceProperty(void *,_DO_DEVINFO_DATA *,ulong)
0x18002146b  mov     rdi, rax
0x18002146e  test    rax, rax
0x180021471  jz      short loc_1800214D3
0x180021473  or      r8, 0FFFFFFFFFFFFFFFFh
0x180021477  inc     r8
0x18002147a  cmp     [rax+r8*2], r14w
0x18002147f  jnz     short loc_180021477
0x180021481  mov     rdx, rax
0x180021484  mov     rcx, rbp
0x180021487  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002148c  mov     ebx, r14d
0x18002148f  mov     rcx, rdi; hMem
0x180021492  call    cs:__imp_LocalFree
0x180021498  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002149c  jz      short loc_1800214A7
0x18002149e  mov     rcx, rsi
0x1800214a1  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800214a7  mov     eax, ebx
0x1800214a9  mov     rcx, [rsp+88h+var_28]
0x1800214ae  xor     rcx, rsp; StackCookie
0x1800214b1  call    __security_check_cookie
0x1800214b6  lea     r11, [rsp+88h+var_18]
0x1800214bb  mov     rbx, [r11+30h]
0x1800214bf  mov     rbp, [r11+38h]
0x1800214c3  mov     rsp, r11
0x1800214c6  pop     r14
0x1800214c8  pop     rdi
0x1800214c9  pop     rsi
0x1800214ca  retn
0x1800214cb  mov     rbx, [rbx]
0x1800214ce  jmp     loc_18002143E
0x1800214d3  call    cs:__imp_GetLastError
0x1800214d9  mov     ebx, eax
0x1800214db  test    eax, eax
0x1800214dd  jnz     short loc_1800214E6
0x1800214df  test    rdi, rdi
0x1800214e2  jnz     short loc_18002148F
0x1800214e4  jmp     short loc_180021498
0x1800214e6  lea     rdx, qword_18009CA18
0x1800214ed  mov     rcx, rbp
0x1800214f0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800214f5  jmp     short loc_1800214DF
```
