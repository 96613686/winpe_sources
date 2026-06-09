# AllocateAndCreateWellKnownAcl(ulong,WELL_KNOWN_SID_TYPE * const,ulong * const,int,_ACL * *,ulong *)

- ea: `0x1800028f8`
- end: `0x180002a57`
- name: `?AllocateAndCreateWellKnownAcl@@YAJKQEAW4WELL_KNOWN_SID_TYPE@@QEAKHPEAPEAU_ACL@@PEAK@Z`
- size: `351`
- prototype: `__int64 __fastcall(unsigned int, enum WELL_KNOWN_SID_TYPE *const, unsigned int *const, int, struct _ACL **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180002e34`

## callees

- `0x1800028f8`
- `0x180002a60`

## import_xrefs

- `ADVAPI32!AddAccessAllowedAce` at `0x1800029d4`
- `ADVAPI32!AddAccessAllowedAce` at `0x1800029d4`
- `ADVAPI32!InitializeAcl` at `0x180002979`
- `ADVAPI32!InitializeAcl` at `0x180002979`
- `KERNEL32!GetLastError` at `0x180002983`
- `KERNEL32!GetLastError` at `0x180002a06`
- `KERNEL32!GetLastError` at `0x180002983`
- `KERNEL32!GetLastError` at `0x180002a06`
- `KERNEL32!LocalFree` at `0x1800029e6`
- `KERNEL32!LocalFree` at `0x180002a23`
- `KERNEL32!LocalFree` at `0x180002a37`
- `KERNEL32!LocalFree` at `0x1800029e6`
- `KERNEL32!LocalFree` at `0x180002a23`
- `KERNEL32!LocalFree` at `0x180002a37`
- `KERNEL32!LocalAlloc` at `0x180002956`
- `KERNEL32!LocalAlloc` at `0x180002956`

## pseudocode

```c
__int64 __fastcall AllocateAndCreateWellKnownAcl(
        __int64 a1,
        enum WELL_KNOWN_SID_TYPE *const a2,
        unsigned int *const a3,
        __int64 a4,
        struct _ACL **a5,
        unsigned int *a6)
{
  ACL *v7; // rax
  struct _ACL *v8; // rsi
  unsigned int v9; // ebx
  signed int v10; // eax
  __int64 v11; // rbp
  int v12; // eax
  PSID v13; // rdi
  signed int LastError; // eax
  PSID pSid; // [rsp+20h] [rbp-58h] BYREF

  pSid = 0;
  if ( !a5 || *a5 || !a6 )
    return 2147942487LL;
  *a6 = 0;
  v7 = (ACL *)LocalAlloc(0x40u, 0xA0u);
  v8 = v7;
  if ( v7 )
  {
    if ( InitializeAcl(v7, 0xA0u, 2u) )
    {
      v11 = 0;
      while ( 1 )
      {
        v12 = AllocateAndCreateWellKnownSid(a2[v11], &pSid);
        v13 = pSid;
        v9 = v12;
        if ( v12 < 0 )
          break;
        if ( !AddAccessAllowedAce(v8, 2u, a3[v11], pSid) )
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
          break;
        }
        if ( v13 )
        {
          LocalFree(v13);
          v13 = 0;
          pSid = 0;
        }
        v11 = (unsigned int)(v11 + 1);
        if ( (unsigned int)v11 >= 2 )
        {
          *a5 = v8;
          *a6 = 160;
          break;
        }
      }
      if ( v13 )
        LocalFree(v13);
    }
    else
    {
      v10 = GetLastError();
      v9 = v10;
      if ( v10 > 0 )
        v9 = (unsigned __int16)v10 | 0x80070000;
    }
  }
  else
  {
    v9 = -2147024882;
  }
  if ( !*a5 )
  {
    if ( v8 )
      LocalFree(v8);
  }
  return v9;
}

```

## disassembly

```asm
0x1800028f8  mov     [rsp+arg_10], r8
0x1800028fd  push    rbx
0x1800028fe  push    rbp
0x1800028ff  push    rsi
0x180002900  push    rdi
0x180002901  push    r12
0x180002903  push    r13
0x180002905  push    r14
0x180002907  push    r15
0x180002909  sub     rsp, 38h
0x18000290d  mov     r14, [rsp+78h+arg_20]
0x180002915  mov     r13, rdx
0x180002918  mov     [rsp+78h+pSid], 0
0x180002921  test    r14, r14
0x180002924  jz      loc_180002A41
0x18000292a  cmp     qword ptr [r14], 0
0x18000292e  jnz     loc_180002A41
0x180002934  mov     r15, [rsp+78h+arg_28]
0x18000293c  test    r15, r15
0x18000293f  jz      loc_180002A41
0x180002945  mov     ebx, 0A0h
0x18000294a  mov     dword ptr [r15], 0
0x180002951  mov     edx, ebx; uBytes
0x180002953  lea     ecx, [rbx-60h]; uFlags
0x180002956  call    cs:__imp_LocalAlloc
0x18000295c  mov     rsi, rax
0x18000295f  test    rax, rax
0x180002962  jnz     short loc_18000296E
0x180002964  mov     ebx, 8007000Eh
0x180002969  jmp     loc_180002A29
0x18000296e  mov     r8d, 2; dwAclRevision
0x180002974  mov     edx, ebx; nAclLength
0x180002976  mov     rcx, rsi; pAcl
0x180002979  call    cs:__imp_InitializeAcl
0x18000297f  test    eax, eax
0x180002981  jnz     short loc_1800029A1
0x180002983  call    cs:__imp_GetLastError
0x180002989  mov     ebx, eax
0x18000298b  test    eax, eax
0x18000298d  jle     loc_180002A29
0x180002993  movzx   ebx, ax
0x180002996  or      ebx, 80070000h
0x18000299c  jmp     loc_180002A29
0x1800029a1  xor     ebp, ebp
0x1800029a3  mov     ecx, [r13+rbp*4+0]; WellKnownSidType
0x1800029a8  lea     rdx, [rsp+78h+pSid]; void **
0x1800029ad  call    ?AllocateAndCreateWellKnownSid@@YAJW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x1800029b2  mov     rdi, [rsp+78h+pSid]
0x1800029b7  mov     ebx, eax
0x1800029b9  test    eax, eax
0x1800029bb  js      short loc_180002A1B
0x1800029bd  mov     rax, [rsp+78h+arg_10]
0x1800029c5  mov     r9, rdi; pSid
0x1800029c8  mov     edx, 2; dwAceRevision
0x1800029cd  mov     rcx, rsi; pAcl
0x1800029d0  mov     r8d, [rax+rbp*4]; AccessMask
0x1800029d4  call    cs:__imp_AddAccessAllowedAce
0x1800029da  test    eax, eax
0x1800029dc  jz      short loc_180002A06
0x1800029de  test    rdi, rdi
0x1800029e1  jz      short loc_1800029F3
0x1800029e3  mov     rcx, rdi; hMem
0x1800029e6  call    cs:__imp_LocalFree
0x1800029ec  xor     edi, edi
0x1800029ee  mov     [rsp+78h+pSid], rdi
0x1800029f3  inc     ebp
0x1800029f5  cmp     ebp, 2
0x1800029f8  jb      short loc_1800029A3
0x1800029fa  mov     [r14], rsi
0x1800029fd  mov     dword ptr [r15], 0A0h
0x180002a04  jmp     short loc_180002A1B
0x180002a06  call    cs:__imp_GetLastError
0x180002a0c  mov     ebx, eax
0x180002a0e  test    eax, eax
0x180002a10  jle     short loc_180002A1B
0x180002a12  movzx   ebx, ax
0x180002a15  or      ebx, 80070000h
0x180002a1b  test    rdi, rdi
0x180002a1e  jz      short loc_180002A29
0x180002a20  mov     rcx, rdi; hMem
0x180002a23  call    cs:__imp_LocalFree
0x180002a29  cmp     qword ptr [r14], 0
0x180002a2d  jnz     short loc_180002A3D
0x180002a2f  test    rsi, rsi
0x180002a32  jz      short loc_180002A3D
0x180002a34  mov     rcx, rsi; hMem
0x180002a37  call    cs:__imp_LocalFree
0x180002a3d  mov     eax, ebx
0x180002a3f  jmp     short loc_180002A46
0x180002a41  mov     eax, 80070057h
0x180002a46  add     rsp, 38h
0x180002a4a  pop     r15
0x180002a4c  pop     r14
0x180002a4e  pop     r13
0x180002a50  pop     r12
0x180002a52  pop     rdi
0x180002a53  pop     rsi
0x180002a54  pop     rbp
0x180002a55  pop     rbx
0x180002a56  retn
```
