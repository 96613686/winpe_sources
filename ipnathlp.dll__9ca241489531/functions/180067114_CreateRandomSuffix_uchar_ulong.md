# CreateRandomSuffix(uchar *,ulong)

- ea: `0x180067114`
- end: `0x1800672b1`
- name: `?CreateRandomSuffix@@YAKPEAEK@Z`
- size: `413`
- prototype: `__int64 __fastcall(BYTE *pbBuffer)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180067574`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18004e0c0`
- `0x180067114`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800671de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006721c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800671de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006721c`
- `RPCRT4!UuidCreate` at `0x18006717d`
- `RPCRT4!UuidCreate` at `0x18006717d`
- `CRYPTSP!CryptGenRandom` at `0x180067212`
- `CRYPTSP!CryptGenRandom` at `0x180067212`
- `CRYPTSP!CryptAcquireContextW` at `0x1800671d4`
- `CRYPTSP!CryptAcquireContextW` at `0x1800671d4`
- `CRYPTSP!CryptReleaseContext` at `0x180067266`
- `CRYPTSP!CryptReleaseContext` at `0x180067266`

## pseudocode

```c
__int64 __fastcall CreateRandomSuffix(BYTE *pbBuffer)
{
  unsigned int v2; // eax
  DWORD LastError; // eax
  DWORD v4; // ebx
  PVOID *v5; // rcx
  __int64 v6; // rdx
  HCRYPTPROV phProv; // [rsp+30h] [rbp-48h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids);
  }
  phProv = 0;
  Uuid = 0;
  v2 = UuidCreate(&Uuid);
  if ( v2
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids, v2);
  }
  *(UUID *)pbBuffer = Uuid;
  if ( CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000040) )
  {
    v4 = 0;
    if ( CryptGenRandom(phProv, 0x10u, pbBuffer) )
    {
LABEL_21:
      v5 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_22;
    }
    LastError = GetLastError();
    v4 = LastError;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 33;
      goto LABEL_20;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 32;
LABEL_20:
      WPP_SF_d(v5[2], v6, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids, LastError);
      goto LABEL_21;
    }
  }
LABEL_22:
  if ( phProv )
  {
    CryptReleaseContext(phProv, 0);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && *((char *)v5 + 28) < 0 && *((_BYTE *)v5 + 25) >= 6u )
    WPP_SF_d(v5[2], 34, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180067114  push    rbx
0x180067116  push    rbp
0x180067117  push    rdi
0x180067118  push    r14
0x18006711a  sub     rsp, 58h
0x18006711e  mov     rax, cs:__security_cookie
0x180067125  xor     rax, rsp
0x180067128  mov     [rsp+78h+var_30], rax
0x18006712d  mov     rdi, rcx
0x180067130  mov     rcx, cs:WPP_GLOBAL_Control
0x180067137  lea     rbp, WPP_GLOBAL_Control
0x18006713e  lea     r14, WPP_cf8b9ea6895b340364ad47c75b8fb1d2_Traceguids
0x180067145  cmp     rcx, rbp
0x180067148  jz      short loc_180067167
0x18006714a  test    byte ptr [rcx+1Ch], 80h
0x18006714e  jz      short loc_180067167
0x180067150  cmp     byte ptr [rcx+19h], 6
0x180067154  jb      short loc_180067167
0x180067156  mov     rcx, [rcx+10h]
0x18006715a  mov     edx, 1Eh
0x18006715f  mov     r8, r14
0x180067162  call    WPP_SF_
0x180067167  xorps   xmm0, xmm0
0x18006716a  mov     [rsp+78h+phProv], 0
0x180067173  lea     rcx, [rsp+78h+Uuid]; Uuid
0x180067178  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x18006717d  call    cs:__imp_UuidCreate
0x180067183  test    eax, eax
0x180067185  jz      short loc_1800671B3
0x180067187  mov     rcx, cs:WPP_GLOBAL_Control
0x18006718e  cmp     rcx, rbp
0x180067191  jz      short loc_1800671B3
0x180067193  test    byte ptr [rcx+1Ch], 80h
0x180067197  jz      short loc_1800671B3
0x180067199  cmp     byte ptr [rcx+19h], 2
0x18006719d  jb      short loc_1800671B3
0x18006719f  mov     rcx, [rcx+10h]
0x1800671a3  mov     edx, 1Fh
0x1800671a8  mov     r9d, eax
0x1800671ab  mov     r8, r14
0x1800671ae  call    WPP_SF_d
0x1800671b3  movups  xmm0, xmmword ptr [rsp+78h+Uuid.Data1]
0x1800671b8  mov     r9d, 1; dwProvType
0x1800671be  mov     [rsp+78h+dwFlags], 0F0000040h; dwFlags
0x1800671c6  xor     r8d, r8d; szProvider
0x1800671c9  lea     rcx, [rsp+78h+phProv]; phProv
0x1800671ce  xor     edx, edx; szContainer
0x1800671d0  movdqu  xmmword ptr [rdi], xmm0
0x1800671d4  call    cs:__imp_CryptAcquireContextW
0x1800671da  test    eax, eax
0x1800671dc  jnz     short loc_180067205
0x1800671de  call    cs:__imp_GetLastError
0x1800671e4  mov     ebx, eax
0x1800671e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800671ed  cmp     rcx, rbp
0x1800671f0  jz      short loc_180067257
0x1800671f2  test    byte ptr [rcx+1Ch], 80h
0x1800671f6  jz      short loc_180067257
0x1800671f8  cmp     byte ptr [rcx+19h], 2
0x1800671fc  jb      short loc_180067257
0x1800671fe  mov     edx, 20h ; ' '
0x180067203  jmp     short loc_180067241
0x180067205  mov     rcx, [rsp+78h+phProv]; hProv
0x18006720a  xor     ebx, ebx
0x18006720c  mov     r8, rdi; pbBuffer
0x18006720f  lea     edx, [rbx+10h]; dwLen
0x180067212  call    cs:__imp_CryptGenRandom
0x180067218  test    eax, eax
0x18006721a  jnz     short loc_180067250
0x18006721c  call    cs:__imp_GetLastError
0x180067222  mov     ebx, eax
0x180067224  mov     rcx, cs:WPP_GLOBAL_Control
0x18006722b  cmp     rcx, rbp
0x18006722e  jz      short loc_180067257
0x180067230  test    byte ptr [rcx+1Ch], 80h
0x180067234  jz      short loc_180067257
0x180067236  cmp     byte ptr [rcx+19h], 2
0x18006723a  jb      short loc_180067257
0x18006723c  mov     edx, 21h ; '!'
0x180067241  mov     rcx, [rcx+10h]
0x180067245  mov     r9d, eax
0x180067248  mov     r8, r14
0x18006724b  call    WPP_SF_d
0x180067250  mov     rcx, cs:WPP_GLOBAL_Control
0x180067257  mov     rax, [rsp+78h+phProv]
0x18006725c  test    rax, rax
0x18006725f  jz      short loc_180067273
0x180067261  xor     edx, edx; dwFlags
0x180067263  mov     rcx, rax; hProv
0x180067266  call    cs:__imp_CryptReleaseContext
0x18006726c  mov     rcx, cs:WPP_GLOBAL_Control
0x180067273  cmp     rcx, rbp
0x180067276  jz      short loc_180067298
0x180067278  test    byte ptr [rcx+1Ch], 80h
0x18006727c  jz      short loc_180067298
0x18006727e  cmp     byte ptr [rcx+19h], 6
0x180067282  jb      short loc_180067298
0x180067284  mov     rcx, [rcx+10h]
0x180067288  mov     edx, 22h ; '"'
0x18006728d  mov     r9d, ebx
0x180067290  mov     r8, r14
0x180067293  call    WPP_SF_d
0x180067298  mov     eax, ebx
0x18006729a  mov     rcx, [rsp+78h+var_30]
0x18006729f  xor     rcx, rsp; StackCookie
0x1800672a2  call    __security_check_cookie
0x1800672a7  add     rsp, 58h
0x1800672ab  pop     r14
0x1800672ad  pop     rdi
0x1800672ae  pop     rbp
0x1800672af  pop     rbx
0x1800672b0  retn
```
