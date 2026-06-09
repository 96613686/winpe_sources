# StopLPD

- ea: `0x180009eb8`
- end: `0x18000a031`
- name: `StopLPD`
- size: `377`
- prototype: `int()`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007c10`

## callees

- `0x180002e7c`
- `0x180009eb8`
- `0x18000a038`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180009f7a`
- `KERNEL32!WaitForSingleObject` at `0x180009ff3`
- `KERNEL32!WaitForSingleObject` at `0x180009f7a`
- `KERNEL32!WaitForSingleObject` at `0x180009ff3`
- `KERNEL32!EnterCriticalSection` at `0x180009fa5`
- `KERNEL32!EnterCriticalSection` at `0x180009fa5`
- `KERNEL32!CloseHandle` at `0x180009f85`
- `KERNEL32!CloseHandle` at `0x180009f85`
- `KERNEL32!LeaveCriticalSection` at `0x180009fbc`
- `KERNEL32!LeaveCriticalSection` at `0x180009fbc`
- `WS2_32!__imp_WSACleanup` at `0x18000a02a`

## pseudocode

```c
int StopLPD()
{
  int v0; // esi
  _QWORD *v1; // rcx
  unsigned int i; // ebx
  __int64 v3; // rdi

  v0 = 0;
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
    v1 = WPP_GLOBAL_Control;
  }
  fShuttingDownGLB = 1;
  for ( i = 0; i < 2; ++i )
  {
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 1) != 0 )
    {
      WPP_SF_(v1[2], 19, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
      v1 = WPP_GLOBAL_Control;
    }
    v3 = 4LL * (int)i;
    if ( family[v3 + 2] != -1 )
    {
      SureCloseSocket(family[v3 + 2]);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
      WaitForSingleObject((HANDLE)family[v3 + 1], 0xFFFFFFFF);
      CloseHandle((HANDLE)family[v3 + 1]);
      v1 = WPP_GLOBAL_Control;
    }
  }
  EnterCriticalSection(&csConnSemGLB);
  if ( (int)Common > 0 )
    v0 = 1;
  LeaveCriticalSection(&csConnSemGLB);
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
    WaitForSingleObject(hEventLastThreadGLB, 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
  }
  return WSACleanup();
}

```

## disassembly

```asm
0x180009eb8  push    rbx
0x180009eba  push    rbp
0x180009ebb  push    rsi
0x180009ebc  push    rdi
0x180009ebd  push    r12
0x180009ebf  push    r14
0x180009ec1  push    r15
0x180009ec3  sub     rsp, 20h
0x180009ec7  xor     esi, esi
0x180009ec9  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ed0  lea     rbp, WPP_GLOBAL_Control
0x180009ed7  lea     r14d, [rsi+1]
0x180009edb  lea     r15, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x180009ee2  cmp     rcx, rbp
0x180009ee5  jz      short loc_180009F03
0x180009ee7  test    [rcx+1Ch], r14b
0x180009eeb  jz      short loc_180009F03
0x180009eed  mov     rcx, [rcx+10h]
0x180009ef1  lea     edx, [rsi+15h]
0x180009ef4  mov     r8, r15
0x180009ef7  call    WPP_SF_
0x180009efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f03  mov     cs:fShuttingDownGLB, r14d
0x180009f0a  lea     r12, family
0x180009f11  xor     ebx, ebx
0x180009f13  cmp     rcx, rbp
0x180009f16  jz      short loc_180009F36
0x180009f18  test    [rcx+1Ch], r14b
0x180009f1c  jz      short loc_180009F36
0x180009f1e  mov     rcx, [rcx+10h]
0x180009f22  mov     edx, 13h
0x180009f27  mov     r8, r15
0x180009f2a  call    WPP_SF_
0x180009f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f36  movsxd  rdi, ebx
0x180009f39  shl     rdi, 5
0x180009f3d  cmp     qword ptr [rdi+r12+10h], 0FFFFFFFFFFFFFFFFh
0x180009f43  jz      short loc_180009F92
0x180009f45  mov     rcx, [rdi+r12+10h]; s
0x180009f4a  call    SureCloseSocket
0x180009f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f56  cmp     rcx, rbp
0x180009f59  jz      short loc_180009F72
0x180009f5b  test    byte ptr [rcx+1Ch], 2
0x180009f5f  jz      short loc_180009F72
0x180009f61  mov     rcx, [rcx+10h]
0x180009f65  mov     edx, 14h
0x180009f6a  mov     r8, r15
0x180009f6d  call    WPP_SF_
0x180009f72  mov     rcx, [rdi+r12+8]; hHandle
0x180009f77  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009f7a  call    cs:__imp_WaitForSingleObject
0x180009f80  mov     rcx, [rdi+r12+8]; hObject
0x180009f85  call    cs:__imp_CloseHandle
0x180009f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f92  add     ebx, r14d
0x180009f95  cmp     ebx, 2
0x180009f98  jb      loc_180009F13
0x180009f9e  lea     rcx, csConnSemGLB; lpCriticalSection
0x180009fa5  call    cs:__imp_EnterCriticalSection
0x180009fab  cmp     dword ptr cs:Common, esi
0x180009fb1  lea     rcx, csConnSemGLB; lpCriticalSection
0x180009fb8  cmovg   esi, r14d
0x180009fbc  call    cs:__imp_LeaveCriticalSection
0x180009fc2  test    esi, esi
0x180009fc4  jz      short loc_18000A01C
0x180009fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fcd  cmp     rcx, rbp
0x180009fd0  jz      short loc_180009FE9
0x180009fd2  test    byte ptr [rcx+1Ch], 2
0x180009fd6  jz      short loc_180009FE9
0x180009fd8  mov     rcx, [rcx+10h]
0x180009fdc  mov     edx, 16h
0x180009fe1  mov     r8, r15
0x180009fe4  call    WPP_SF_
0x180009fe9  mov     rcx, cs:hEventLastThreadGLB; hHandle
0x180009ff0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009ff3  call    cs:__imp_WaitForSingleObject
0x180009ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a000  cmp     rcx, rbp
0x18000a003  jz      short loc_18000A01C
0x18000a005  test    byte ptr [rcx+1Ch], 2
0x18000a009  jz      short loc_18000A01C
0x18000a00b  mov     rcx, [rcx+10h]
0x18000a00f  mov     edx, 17h
0x18000a014  mov     r8, r15
0x18000a017  call    WPP_SF_
0x18000a01c  add     rsp, 20h
0x18000a020  pop     r15
0x18000a022  pop     r14
0x18000a024  pop     r12
0x18000a026  pop     rdi
0x18000a027  pop     rsi
0x18000a028  pop     rbp
0x18000a029  pop     rbx
0x18000a02a  jmp     cs:__imp_WSACleanup
```
