# CFaxSecurity::GetSecurity(ulong,void * *,int)

- ea: `0x180013fa0`
- end: `0x180014123`
- name: `?GetSecurity@CFaxSecurity@@UEAAJKPEAPEAXH@Z`
- size: `387`
- prototype: `__int64 __fastcall(CFaxSecurity *__hidden this, unsigned int, void **, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000e3b4`
- `0x18000e5b0`
- `0x18000e7b0`
- `0x180013fa0`

## import_xrefs

- `FXSAPI!FaxGetSecurityEx2` at `0x18001405b`
- `FXSAPI!FaxGetSecurityEx2` at `0x18001405b`
- `FXSAPI!FaxFreeBuffer` at `0x180014104`
- `FXSAPI!FaxFreeBuffer` at `0x180014104`
- `KERNEL32!GetLastError` at `0x180014065`
- `KERNEL32!GetLastError` at `0x180014065`

## string_xrefs

- `0x180014041`: `SeSecurityPrivilege`

## pseudocode

```c
__int64 __fastcall CFaxSecurity::GetSecurity(CFaxSecurity *this, unsigned int a2, void **a3, int a4)
{
  _QWORD *v8; // rcx
  __int64 v10; // rsi
  DWORD LastError; // eax
  int v12; // ebx
  unsigned int SelfRelativeCopy; // eax
  int v14; // edi
  LPVOID Buffer[9]; // [rsp+20h] [rbp-48h] BYREF

  Buffer[0] = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( a4 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x100) != 0 && *((_BYTE *)v8 + 25) >= 2u )
      WPP_SF_(v8[2], 18, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids);
    return 2147500033LL;
  }
  v10 = -1;
  if ( (a2 & 8) != 0 )
    v10 = EnablePrivilege(L"SeSecurityPrivilege");
  if ( !(unsigned int)FaxGetSecurityEx2(*((_QWORD *)this + 1), a2, Buffer) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids, LastError);
    }
    if ( v12 <= 0 )
      goto LABEL_29;
    v12 = (unsigned __int16)v12;
    goto LABEL_28;
  }
  v12 = 0;
  SelfRelativeCopy = MakeSelfRelativeCopy(Buffer[0], a3);
  v14 = SelfRelativeCopy;
  if ( SelfRelativeCopy )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids,
        SelfRelativeCopy);
    }
    if ( v14 > 0 )
    {
      v12 = (unsigned __int16)v14;
LABEL_28:
      v12 |= 0x80070000;
      goto LABEL_29;
    }
    v12 = v14;
  }
LABEL_29:
  if ( Buffer[0] )
    FaxFreeBuffer(Buffer[0]);
  ReleasePrivilege((HANDLE)v10);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180013fa0  push    rbx
0x180013fa2  push    rbp
0x180013fa3  push    rsi
0x180013fa4  push    rdi
0x180013fa5  push    r12
0x180013fa7  push    r14
0x180013fa9  push    r15
0x180013fab  sub     rsp, 30h
0x180013faf  mov     edi, r9d
0x180013fb2  mov     [rsp+68h+Buffer], 0
0x180013fbb  mov     rbp, r8
0x180013fbe  mov     ebx, edx
0x180013fc0  mov     r14, rcx
0x180013fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fca  lea     r12, WPP_GLOBAL_Control
0x180013fd1  mov     r15d, 100h
0x180013fd7  cmp     rcx, r12
0x180013fda  jz      short loc_180014004
0x180013fdc  test    [rcx+1Ch], r15d
0x180013fe0  jz      short loc_180014004
0x180013fe2  cmp     byte ptr [rcx+19h], 5
0x180013fe6  jb      short loc_180014004
0x180013fe8  mov     rcx, [rcx+10h]
0x180013fec  lea     r8, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids
0x180013ff3  mov     edx, 11h
0x180013ff8  call    WPP_SF_
0x180013ffd  mov     rcx, cs:WPP_GLOBAL_Control
0x180014004  test    edi, edi
0x180014006  jz      short loc_180014038
0x180014008  cmp     rcx, r12
0x18001400b  jz      short loc_18001402E
0x18001400d  test    [rcx+1Ch], r15d
0x180014011  jz      short loc_18001402E
0x180014013  cmp     byte ptr [rcx+19h], 2
0x180014017  jb      short loc_18001402E
0x180014019  mov     rcx, [rcx+10h]
0x18001401d  lea     r8, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids
0x180014024  mov     edx, 12h
0x180014029  call    WPP_SF_
0x18001402e  mov     eax, 80004001h
0x180014033  jmp     loc_180014114
0x180014038  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001403c  test    bl, 8
0x18001403f  jz      short loc_180014050
0x180014041  lea     rcx, aSesecuritypriv; "SeSecurityPrivilege"
0x180014048  call    EnablePrivilege
0x18001404d  mov     rsi, rax
0x180014050  mov     rcx, [r14+8]
0x180014054  lea     r8, [rsp+68h+Buffer]
0x180014059  mov     edx, ebx
0x18001405b  call    cs:__imp_FaxGetSecurityEx2
0x180014061  test    eax, eax
0x180014063  jnz     short loc_1800140A6
0x180014065  call    cs:__imp_GetLastError
0x18001406b  mov     ebx, eax
0x18001406d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014074  cmp     rcx, r12
0x180014077  jz      short loc_18001409D
0x180014079  test    [rcx+1Ch], r15d
0x18001407d  jz      short loc_18001409D
0x18001407f  cmp     byte ptr [rcx+19h], 2
0x180014083  jb      short loc_18001409D
0x180014085  mov     rcx, [rcx+10h]
0x180014089  lea     r8, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids
0x180014090  mov     edx, 13h
0x180014095  mov     r9d, eax
0x180014098  call    WPP_SF_d
0x18001409d  test    ebx, ebx
0x18001409f  jle     short loc_1800140FA
0x1800140a1  movzx   ebx, bx
0x1800140a4  jmp     short loc_1800140F4
0x1800140a6  mov     rcx, [rsp+68h+Buffer]; Src
0x1800140ab  mov     rdx, rbp
0x1800140ae  xor     ebx, ebx
0x1800140b0  call    MakeSelfRelativeCopy
0x1800140b5  mov     edi, eax
0x1800140b7  test    eax, eax
0x1800140b9  jz      short loc_1800140FA
0x1800140bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140c2  cmp     rcx, r12
0x1800140c5  jz      short loc_1800140E9
0x1800140c7  test    [rcx+1Ch], r15d
0x1800140cb  jz      short loc_1800140E9
0x1800140cd  cmp     byte ptr [rcx+19h], 2
0x1800140d1  jb      short loc_1800140E9
0x1800140d3  mov     rcx, [rcx+10h]
0x1800140d7  lea     edx, [rbx+14h]
0x1800140da  mov     r9d, eax
0x1800140dd  lea     r8, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids
0x1800140e4  call    WPP_SF_d
0x1800140e9  test    edi, edi
0x1800140eb  jg      short loc_1800140F1
0x1800140ed  mov     ebx, edi
0x1800140ef  jmp     short loc_1800140FA
0x1800140f1  movzx   ebx, di
0x1800140f4  or      ebx, 80070000h
0x1800140fa  mov     rcx, [rsp+68h+Buffer]; Buffer
0x1800140ff  test    rcx, rcx
0x180014102  jz      short loc_18001410A
0x180014104  call    cs:__imp_FaxFreeBuffer
0x18001410a  mov     rcx, rsi; hObject
0x18001410d  call    ReleasePrivilege
0x180014112  mov     eax, ebx
0x180014114  add     rsp, 30h
0x180014118  pop     r15
0x18001411a  pop     r14
0x18001411c  pop     r12
0x18001411e  pop     rdi
0x18001411f  pop     rsi
0x180014120  pop     rbp
0x180014121  pop     rbx
0x180014122  retn
```
