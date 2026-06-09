# DfdManager::CreateGuid(ushort *,ulong)

- ea: `0x180006418`
- end: `0x1800064f3`
- name: `?CreateGuid@DfdManager@@AEAAKPEAGK@Z`
- size: `219`
- prototype: `__int64 __fastcall(DfdManager *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005dac`

## callees

- `0x180002c68`
- `0x180002c90`
- `0x180006418`
- `0x180008370`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000649b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000649b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000644e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000644e`

## pseudocode

```c
__int64 __fastcall DfdManager::CreateGuid(DfdManager *this, unsigned __int16 *a2)
{
  HRESULT v4; // ebx
  GUID pguid; // [rsp+20h] [rbp-28h] BYREF

  pguid = 0;
  if ( !a2 )
    return 87;
  v4 = CoCreateGuid(&pguid);
  if ( v4 >= 0 )
  {
    if ( !StringFromGUID2(&pguid, a2, 128) )
    {
      LOWORD(v4) = 16389;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids, (unsigned int)v4);
  }
  return (unsigned __int16)v4;
}

```

## disassembly

```asm
0x180006418  mov     [rsp+arg_0], rbx
0x18000641d  push    rdi
0x18000641e  sub     rsp, 40h
0x180006422  mov     rax, cs:__security_cookie
0x180006429  xor     rax, rsp
0x18000642c  mov     [rsp+48h+var_18], rax
0x180006431  xorps   xmm0, xmm0
0x180006434  mov     rdi, rdx
0x180006437  movups  xmmword ptr [rsp+48h+pguid.Data1], xmm0
0x18000643c  test    rdx, rdx
0x18000643f  jnz     short loc_180006449
0x180006441  lea     eax, [rdx+57h]
0x180006444  jmp     loc_1800064DB
0x180006449  lea     rcx, [rsp+48h+pguid]; pguid
0x18000644e  call    cs:__imp_CoCreateGuid
0x180006454  mov     ebx, eax
0x180006456  test    eax, eax
0x180006458  jns     short loc_18000648D
0x18000645a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006461  lea     rax, WPP_GLOBAL_Control
0x180006468  cmp     rcx, rax
0x18000646b  jz      short loc_1800064D8
0x18000646d  test    byte ptr [rcx+1Ch], 1
0x180006471  jz      short loc_1800064D8
0x180006473  mov     rcx, [rcx+10h]
0x180006477  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x18000647e  mov     edx, 20h ; ' '
0x180006483  mov     r9d, ebx
0x180006486  call    WPP_SF_d
0x18000648b  jmp     short loc_1800064D8
0x18000648d  mov     r8d, 80h; cchMax
0x180006493  lea     rcx, [rsp+48h+pguid]; rguid
0x180006498  mov     rdx, rdi; lpsz
0x18000649b  call    cs:__imp_StringFromGUID2
0x1800064a1  test    eax, eax
0x1800064a3  jnz     short loc_1800064D8
0x1800064a5  mov     ebx, 80004005h
0x1800064aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064b1  lea     rax, WPP_GLOBAL_Control
0x1800064b8  cmp     rcx, rax
0x1800064bb  jz      short loc_1800064D8
0x1800064bd  test    byte ptr [rcx+1Ch], 1
0x1800064c1  jz      short loc_1800064D8
0x1800064c3  mov     rcx, [rcx+10h]
0x1800064c7  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x1800064ce  mov     edx, 21h ; '!'
0x1800064d3  call    WPP_SF_
0x1800064d8  movzx   eax, bx
0x1800064db  mov     rcx, [rsp+48h+var_18]
0x1800064e0  xor     rcx, rsp; StackCookie
0x1800064e3  call    __security_check_cookie
0x1800064e8  mov     rbx, [rsp+48h+arg_0]
0x1800064ed  add     rsp, 40h
0x1800064f1  pop     rdi
0x1800064f2  retn
```
