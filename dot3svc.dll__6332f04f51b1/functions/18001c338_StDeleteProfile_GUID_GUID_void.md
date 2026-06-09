# StDeleteProfile(_GUID *,_GUID *,void *)

- ea: `0x18001c338`
- end: `0x18001c42f`
- name: `?StDeleteProfile@@YAKPEAU_GUID@@0PEAX@Z`
- size: `247`
- prototype: `__int64 __fastcall(GUID *rguid, GUID *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000d638`

## callees

- `0x1800025f0`
- `0x180003114`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001c338`
- `0x18001e48c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3d0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001c3c6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001c3c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StDeleteProfile(GUID *rguid, GUID *a2, void *a3)
{
  DWORD ProfileFilePath; // ebx
  unsigned __int64 v7; // [rsp+20h] [rbp-238h]
  WCHAR FileName[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(FileName, 0, 0x208u);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 19, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
  }
  ProfileFilePath = StpGetProfileFilePath(rguid, a2, 0, FileName, v7);
  if ( !ProfileFilePath && !DeleteFileW(FileName) )
    ProfileFilePath = GetLastError();
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 20, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, ProfileFilePath);
  }
  return ProfileFilePath;
}

```

## disassembly

```asm
0x18001c338  mov     [rsp+arg_10], rbx
0x18001c33d  mov     [rsp+arg_18], rsi
0x18001c342  push    rdi
0x18001c343  sub     rsp, 250h
0x18001c34a  mov     rax, cs:__security_cookie
0x18001c351  xor     rax, rsp
0x18001c354  mov     [rsp+258h+var_18], rax
0x18001c35c  mov     rdi, rdx
0x18001c35f  mov     rbx, rcx
0x18001c362  xor     edx, edx; Val
0x18001c364  lea     rcx, [rsp+258h+FileName]; void *
0x18001c369  mov     r8d, 208h; Size
0x18001c36f  call    memset_0
0x18001c374  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c37b  lea     rsi, WPP_GLOBAL_Control
0x18001c382  cmp     rcx, rsi
0x18001c385  jz      short loc_18001C3A8
0x18001c387  cmp     byte ptr [rcx+19h], 4
0x18001c38b  jb      short loc_18001C3A8
0x18001c38d  test    byte ptr [rcx+1Ch], 1
0x18001c391  jz      short loc_18001C3A8
0x18001c393  mov     rcx, [rcx+10h]
0x18001c397  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001c39e  mov     edx, 13h
0x18001c3a3  call    WPP_SF_
0x18001c3a8  lea     r9, [rsp+258h+FileName]; unsigned __int16 *
0x18001c3ad  xor     r8d, r8d; int
0x18001c3b0  mov     rdx, rdi; GUID *
0x18001c3b3  mov     rcx, rbx; rguid
0x18001c3b6  call    ?StpGetProfileFilePath@@YAKPEAU_GUID@@0HPEAG_K@Z; StpGetProfileFilePath(_GUID *,_GUID *,int,ushort *,unsigned __int64)
0x18001c3bb  mov     ebx, eax
0x18001c3bd  test    eax, eax
0x18001c3bf  jnz     short loc_18001C3D8
0x18001c3c1  lea     rcx, [rsp+258h+FileName]; lpFileName
0x18001c3c6  call    cs:__imp_DeleteFileW
0x18001c3cc  test    eax, eax
0x18001c3ce  jnz     short loc_18001C3D8
0x18001c3d0  call    cs:__imp_GetLastError
0x18001c3d6  mov     ebx, eax
0x18001c3d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3df  cmp     rcx, rsi
0x18001c3e2  jz      short loc_18001C408
0x18001c3e4  cmp     byte ptr [rcx+19h], 4
0x18001c3e8  jb      short loc_18001C408
0x18001c3ea  test    byte ptr [rcx+1Ch], 1
0x18001c3ee  jz      short loc_18001C408
0x18001c3f0  mov     rcx, [rcx+10h]
0x18001c3f4  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001c3fb  mov     edx, 14h
0x18001c400  mov     r9d, ebx
0x18001c403  call    WPP_SF_d
0x18001c408  mov     eax, ebx
0x18001c40a  mov     rcx, [rsp+258h+var_18]
0x18001c412  xor     rcx, rsp; StackCookie
0x18001c415  call    __security_check_cookie
0x18001c41a  lea     r11, [rsp+258h+var_8]
0x18001c422  mov     rbx, [r11+20h]
0x18001c426  mov     rsi, [r11+28h]
0x18001c42a  mov     rsp, r11
0x18001c42d  pop     rdi
0x18001c42e  retn
```
