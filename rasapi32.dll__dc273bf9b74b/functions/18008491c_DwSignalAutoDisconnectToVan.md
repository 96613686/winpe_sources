# DwSignalAutoDisconnectToVan

- ea: `0x18008491c`
- end: `0x180084b73`
- name: `DwSignalAutoDisconnectToVan`
- size: `599`
- prototype: `__int64 __fastcall(wchar_t *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180089eac`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x18007e5f0`
- `0x18008491c`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `msvcrt!_wcsupr_s` at `0x180084a50`
- `msvcrt!_wcsupr_s` at `0x180084a50`
- `msvcrt!wcsncat_s` at `0x180084acb`
- `msvcrt!wcsncat_s` at `0x180084acb`
- `msvcrt!wcsncpy_s` at `0x180084a25`
- `msvcrt!wcsncpy_s` at `0x180084a40`
- `msvcrt!wcsncpy_s` at `0x180084a25`
- `msvcrt!wcsncpy_s` at `0x180084a40`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180084b1c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180084b1c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180084b0b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180084b0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084b25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084b25`

## pseudocode

```c
int __fastcall DwSignalAutoDisconnectToVan(wchar_t *Source)
{
  _QWORD *v2; // rbx
  HANDLE v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rdx
  _DWORD *v6; // rcx
  void *v7; // rbx
  wchar_t Destination[2]; // [rsp+20h] [rbp-458h] BYREF
  _BYTE v10[524]; // [rsp+24h] [rbp-454h] BYREF
  wchar_t String[256]; // [rsp+230h] [rbp-248h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 688, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  *(_DWORD *)Destination = 0;
  memset_0(v10, 0, 0x204u);
  LODWORD(v3) = (unsigned int)memset_0(String, 0, sizeof(String));
  if ( Source )
  {
    wcsncpy_s(Destination, 0x104u, L"Global\\Microsoft.Windows.RRAS.Van.AutoDisconnectEvent.", 0xFFFFFFFFFFFFFFFFuLL);
    wcsncpy_s(String, 0x100u, Source, 0xFFFFFFFFFFFFFFFFuLL);
    LODWORD(v3) = _wcsupr_s(String, 0x100u);
    if ( (_DWORD)v3 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return (int)v3;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LODWORD(v3) = WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        691,
                        WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids,
                        (unsigned int)v3);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 == (_DWORD *)&WPP_GLOBAL_Control || (v6[7] & 0x800) == 0 || *((_BYTE *)v6 + 25) < 6u )
        return (int)v3;
      v5 = 692;
    }
    else
    {
      wcsncat_s(Destination, 0x104u, String, 0xFFFFFFFFFFFFFFFFuLL);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 693, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, Destination);
      }
      v3 = OpenEventW(2u, 1, Destination);
      v7 = v3;
      if ( v3 )
      {
        SetEvent(v3);
        LODWORD(v3) = CloseHandle(v7);
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
      {
        return (int)v3;
      }
      v5 = 694;
    }
    v4 = *((_QWORD *)v6 + 2);
    goto LABEL_34;
  }
  if ( v2 != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)v2 + 7) & 0x800) != 0 && *((_BYTE *)v2 + 25) >= 2u )
    {
      LODWORD(v3) = WPP_SF_(v2[2], 689, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x800) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    {
      v4 = v2[2];
      v5 = 690;
LABEL_34:
      LODWORD(v3) = WPP_SF_(v4, v5, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    }
  }
  return (int)v3;
}

```

## disassembly

```asm
0x18008491c  push    rbx
0x18008491e  push    rbp
0x18008491f  push    rsi
0x180084920  push    rdi
0x180084921  push    r12
0x180084923  push    r14
0x180084925  sub     rsp, 448h
0x18008492c  mov     rax, cs:__security_cookie
0x180084933  xor     rax, rsp
0x180084936  mov     [rsp+478h+var_48], rax
0x18008493e  mov     rdi, rcx
0x180084941  mov     rbx, cs:WPP_GLOBAL_Control
0x180084948  lea     rbp, WPP_GLOBAL_Control
0x18008494f  lea     r14, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180084956  mov     esi, 800h
0x18008495b  cmp     rbx, rbp
0x18008495e  jz      short loc_180084983
0x180084960  test    [rbx+1Ch], esi
0x180084963  jz      short loc_180084983
0x180084965  cmp     byte ptr [rbx+19h], 6
0x180084969  jb      short loc_180084983
0x18008496b  mov     rcx, [rbx+10h]
0x18008496f  mov     edx, 2B0h
0x180084974  mov     r8, r14
0x180084977  call    WPP_SF_
0x18008497c  mov     rbx, cs:WPP_GLOBAL_Control
0x180084983  xor     edx, edx; Val
0x180084985  mov     dword ptr [rsp+478h+Destination], 0
0x18008498d  mov     r8d, 204h; Size
0x180084993  lea     rcx, [rsp+478h+var_454]; void *
0x180084998  call    memset_0
0x18008499d  xor     edx, edx; Val
0x18008499f  lea     rcx, [rsp+478h+String]; void *
0x1800849a7  mov     r8d, 200h; Size
0x1800849ad  call    memset_0
0x1800849b2  test    rdi, rdi
0x1800849b5  jnz     short loc_180084A0D
0x1800849b7  cmp     rbx, rbp
0x1800849ba  jz      loc_180084B53
0x1800849c0  test    [rbx+1Ch], esi
0x1800849c3  jz      short loc_1800849E3
0x1800849c5  cmp     byte ptr [rbx+19h], 2
0x1800849c9  jb      short loc_1800849E3
0x1800849cb  mov     rcx, [rbx+10h]
0x1800849cf  mov     edx, 2B1h
0x1800849d4  mov     r8, r14
0x1800849d7  call    WPP_SF_
0x1800849dc  mov     rbx, cs:WPP_GLOBAL_Control
0x1800849e3  cmp     rbx, rbp
0x1800849e6  jz      loc_180084B53
0x1800849ec  test    [rbx+1Ch], esi
0x1800849ef  jz      loc_180084B53
0x1800849f5  cmp     byte ptr [rbx+19h], 6
0x1800849f9  jb      loc_180084B53
0x1800849ff  mov     rcx, [rbx+10h]
0x180084a03  mov     edx, 2B2h
0x180084a08  jmp     loc_180084B4B
0x180084a0d  or      r12, 0FFFFFFFFFFFFFFFFh
0x180084a11  lea     r8, aGlobalMicrosof; "Global\\Microsoft.Windows.RRAS.Van.Auto"...
0x180084a18  mov     r9, r12; MaxCount
0x180084a1b  lea     rcx, [rsp+478h+Destination]; Destination
0x180084a20  mov     edx, 104h; SizeInWords
0x180084a25  call    cs:__imp_wcsncpy_s
0x180084a2b  mov     ebx, 100h
0x180084a30  lea     rcx, [rsp+478h+String]; Destination
0x180084a38  mov     edx, ebx; SizeInWords
0x180084a3a  mov     r9, r12; MaxCount
0x180084a3d  mov     r8, rdi; Source
0x180084a40  call    cs:__imp_wcsncpy_s
0x180084a46  mov     edx, ebx; Size
0x180084a48  lea     rcx, [rsp+478h+String]; String
0x180084a50  call    cs:__imp__wcsupr_s
0x180084a56  test    eax, eax
0x180084a58  jz      short loc_180084AB6
0x180084a5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180084a61  cmp     rcx, rbp
0x180084a64  jz      loc_180084B53
0x180084a6a  test    [rcx+1Ch], esi
0x180084a6d  jz      short loc_180084A90
0x180084a6f  cmp     byte ptr [rcx+19h], 2
0x180084a73  jb      short loc_180084A90
0x180084a75  mov     rcx, [rcx+10h]
0x180084a79  mov     edx, 2B3h
0x180084a7e  mov     r9d, eax
0x180084a81  mov     r8, r14
0x180084a84  call    WPP_SF_d
0x180084a89  mov     rcx, cs:WPP_GLOBAL_Control
0x180084a90  cmp     rcx, rbp
0x180084a93  jz      loc_180084B53
0x180084a99  test    [rcx+1Ch], esi
0x180084a9c  jz      loc_180084B53
0x180084aa2  cmp     byte ptr [rcx+19h], 6
0x180084aa6  jb      loc_180084B53
0x180084aac  mov     edx, 2B4h
0x180084ab1  jmp     loc_180084B47
0x180084ab6  mov     r9, r12; MaxCount
0x180084ab9  lea     r8, [rsp+478h+String]; Source
0x180084ac1  mov     edx, 104h; SizeInWords
0x180084ac6  lea     rcx, [rsp+478h+Destination]; Destination
0x180084acb  call    cs:__imp_wcsncat_s
0x180084ad1  mov     rcx, cs:WPP_GLOBAL_Control
0x180084ad8  cmp     rcx, rbp
0x180084adb  jz      short loc_180084AFE
0x180084add  test    [rcx+1Ch], esi
0x180084ae0  jz      short loc_180084AFE
0x180084ae2  cmp     byte ptr [rcx+19h], 5
0x180084ae6  jb      short loc_180084AFE
0x180084ae8  mov     rcx, [rcx+10h]
0x180084aec  lea     r9, [rsp+478h+Destination]
0x180084af1  mov     edx, 2B5h
0x180084af6  mov     r8, r14
0x180084af9  call    WPP_SF_S
0x180084afe  mov     edx, 1; bInheritHandle
0x180084b03  lea     r8, [rsp+478h+Destination]; lpName
0x180084b08  lea     ecx, [rdx+1]; dwDesiredAccess
0x180084b0b  call    cs:__imp_OpenEventW
0x180084b11  mov     rbx, rax
0x180084b14  test    rax, rax
0x180084b17  jz      short loc_180084B2B
0x180084b19  mov     rcx, rax; hEvent
0x180084b1c  call    cs:__imp_SetEvent
0x180084b22  mov     rcx, rbx; hObject
0x180084b25  call    cs:__imp_CloseHandle
0x180084b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180084b32  cmp     rcx, rbp
0x180084b35  jz      short loc_180084B53
0x180084b37  test    [rcx+1Ch], esi
0x180084b3a  jz      short loc_180084B53
0x180084b3c  cmp     byte ptr [rcx+19h], 6
0x180084b40  jb      short loc_180084B53
0x180084b42  mov     edx, 2B6h
0x180084b47  mov     rcx, [rcx+10h]
0x180084b4b  mov     r8, r14
0x180084b4e  call    WPP_SF_
0x180084b53  mov     rcx, [rsp+478h+var_48]
0x180084b5b  xor     rcx, rsp; StackCookie
0x180084b5e  call    __security_check_cookie
0x180084b63  add     rsp, 448h
0x180084b6a  pop     r14
0x180084b6c  pop     r12
0x180084b6e  pop     rdi
0x180084b6f  pop     rsi
0x180084b70  pop     rbp
0x180084b71  pop     rbx
0x180084b72  retn
```
