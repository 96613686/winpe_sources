# CConfigAdvancedPage::GetArchiveSettings(void)

- ea: `0x180014360`
- end: `0x1800144e1`
- name: `?GetArchiveSettings@CConfigAdvancedPage@@AEAAKXZ`
- size: `385`
- prototype: `unsigned int __fastcall(CConfigAdvancedPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800145b4`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x180014360`

## import_xrefs

- `FXSAPI!FaxGetGeneralConfiguration` at `0x1800143bc`
- `FXSAPI!FaxGetGeneralConfiguration` at `0x1800143bc`
- `FXSAPI!FaxFreeBuffer` at `0x1800144c6`
- `FXSAPI!FaxFreeBuffer` at `0x1800144c6`
- `KERNEL32!GetLastError` at `0x1800143c6`
- `KERNEL32!GetLastError` at `0x1800143c6`

## pseudocode

```c
__int64 __fastcall CConfigAdvancedPage::GetArchiveSettings(CConfigAdvancedPage *this)
{
  DWORD LastError; // eax
  unsigned int v3; // ebx
  _DWORD *v4; // rdx
  _WORD *v5; // r9
  __int64 v6; // rax
  __int64 v7; // r8
  _WORD *v8; // rcx
  _WORD *v9; // rcx
  unsigned int v10; // edi
  LPVOID Buffer; // [rsp+40h] [rbp+8h] BYREF

  Buffer = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids);
  }
  if ( (unsigned int)FaxGetGeneralConfiguration(*((_QWORD *)this + 4), 0, &Buffer) )
  {
    v4 = Buffer;
    v5 = (_WORD *)((char *)this + 40);
    v6 = 2147483646;
    v7 = 260;
    v8 = (_WORD *)*((_QWORD *)Buffer + 1);
    do
    {
      if ( !v6 )
        break;
      if ( !*v8 )
        break;
      *v5++ = *v8++;
      --v6;
      --v7;
    }
    while ( v7 );
    v9 = v5 - 1;
    v10 = v7 == 0 ? 0x8007007A : 0;
    if ( v7 )
      v9 = v5;
    *v9 = 0;
    if ( v7 )
    {
      v3 = 0;
      *((_DWORD *)this + 140) = v4[1];
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids, v10);
        v4 = Buffer;
      }
      v3 = (unsigned __int16)v10;
      if ( (v10 & 0x1FFF0000) != 0x70000 )
        v3 = v10;
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids, LastError);
    }
    v4 = Buffer;
  }
  if ( v4 )
    FaxFreeBuffer(v4);
  return v3;
}

```

## disassembly

```asm
0x180014360  mov     [rsp+arg_8], rbx
0x180014365  mov     [rsp+arg_10], rbp
0x18001436a  push    rsi
0x18001436b  push    rdi
0x18001436c  push    r15
0x18001436e  sub     rsp, 20h
0x180014372  xor     ebp, ebp
0x180014374  mov     rsi, rcx
0x180014377  mov     [rsp+38h+Buffer], rbp
0x18001437c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014383  lea     r15, WPP_GLOBAL_Control
0x18001438a  cmp     rcx, r15
0x18001438d  jz      short loc_1800143B1
0x18001438f  test    dword ptr [rcx+1Ch], 100h
0x180014396  jz      short loc_1800143B1
0x180014398  cmp     byte ptr [rcx+19h], 5
0x18001439c  jb      short loc_1800143B1
0x18001439e  mov     rcx, [rcx+10h]
0x1800143a2  lea     edx, [rbp+0Eh]
0x1800143a5  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x1800143ac  call    WPP_SF_
0x1800143b1  mov     rcx, [rsi+20h]
0x1800143b5  lea     r8, [rsp+38h+Buffer]
0x1800143ba  xor     edx, edx
0x1800143bc  call    cs:__imp_FaxGetGeneralConfiguration
0x1800143c2  test    eax, eax
0x1800143c4  jnz     short loc_18001440B
0x1800143c6  call    cs:__imp_GetLastError
0x1800143cc  mov     ebx, eax
0x1800143ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143d5  cmp     rcx, r15
0x1800143d8  jz      short loc_180014401
0x1800143da  test    dword ptr [rcx+1Ch], 100h
0x1800143e1  jz      short loc_180014401
0x1800143e3  cmp     byte ptr [rcx+19h], 2
0x1800143e7  jb      short loc_180014401
0x1800143e9  mov     rcx, [rcx+10h]
0x1800143ed  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x1800143f4  mov     edx, 0Fh
0x1800143f9  mov     r9d, eax
0x1800143fc  call    WPP_SF_d
0x180014401  mov     rdx, [rsp+38h+Buffer]
0x180014406  jmp     loc_1800144BE
0x18001440b  mov     rdx, [rsp+38h+Buffer]
0x180014410  lea     r9, [rsi+28h]
0x180014414  mov     eax, 7FFFFFFEh
0x180014419  mov     r8d, 104h
0x18001441f  mov     rcx, [rdx+8]
0x180014423  test    rax, rax
0x180014426  jz      short loc_180014447
0x180014428  movzx   r10d, word ptr [rcx]
0x18001442c  test    r10w, r10w
0x180014430  jz      short loc_180014447
0x180014432  mov     [r9], r10w
0x180014436  add     rcx, 2
0x18001443a  add     r9, 2
0x18001443e  dec     rax
0x180014441  sub     r8, 1
0x180014445  jnz     short loc_180014423
0x180014447  mov     rax, r8
0x18001444a  lea     rcx, [r9-2]
0x18001444e  neg     rax
0x180014451  sbb     edi, edi
0x180014453  not     edi
0x180014455  and     edi, 8007007Ah
0x18001445b  test    r8, r8
0x18001445e  cmovnz  rcx, r9
0x180014462  mov     [rcx], bp
0x180014465  jnz     short loc_1800144B3
0x180014467  mov     rcx, cs:WPP_GLOBAL_Control
0x18001446e  cmp     rcx, r15
0x180014471  jz      short loc_18001449F
0x180014473  test    dword ptr [rcx+1Ch], 100h
0x18001447a  jz      short loc_18001449F
0x18001447c  cmp     byte ptr [rcx+19h], 2
0x180014480  jb      short loc_18001449F
0x180014482  mov     rcx, [rcx+10h]
0x180014486  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x18001448d  mov     edx, 10h
0x180014492  mov     r9d, edi
0x180014495  call    WPP_SF_d
0x18001449a  mov     rdx, [rsp+38h+Buffer]
0x18001449f  mov     eax, edi
0x1800144a1  movzx   ebx, di
0x1800144a4  and     eax, 1FFF0000h
0x1800144a9  cmp     eax, 70000h
0x1800144ae  cmovnz  ebx, edi
0x1800144b1  jmp     short loc_1800144BE
0x1800144b3  mov     eax, [rdx+4]
0x1800144b6  mov     ebx, ebp
0x1800144b8  mov     [rsi+230h], eax
0x1800144be  test    rdx, rdx
0x1800144c1  jz      short loc_1800144CC
0x1800144c3  mov     rcx, rdx; Buffer
0x1800144c6  call    cs:__imp_FaxFreeBuffer
0x1800144cc  mov     rbp, [rsp+38h+arg_10]
0x1800144d1  mov     eax, ebx
0x1800144d3  mov     rbx, [rsp+38h+arg_8]
0x1800144d8  add     rsp, 20h
0x1800144dc  pop     r15
0x1800144de  pop     rdi
0x1800144df  pop     rsi
0x1800144e0  retn
```
