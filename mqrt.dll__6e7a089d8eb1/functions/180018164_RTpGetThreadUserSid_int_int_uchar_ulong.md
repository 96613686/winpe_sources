# RTpGetThreadUserSid(int *,int *,uchar * *,ulong *)

- ea: `0x180018164`
- end: `0x18001821a`
- name: `?RTpGetThreadUserSid@@YAJPEAH0PEAPEAEPEAK@Z`
- size: `182`
- prototype: `__int64 __fastcall(int *, int *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180010c70`
- `0x18001753c`

## callees

- `0x180013c74`
- `0x180018164`

## import_xrefs

- `mqsec!MQSec_GetLocalMachineSid` at `0x1800181ee`
- `mqsec!MQSec_GetLocalMachineSid` at `0x1800181ee`
- `mqsec!MQSec_GetThreadUserSid` at `0x1800181c4`
- `mqsec!MQSec_GetThreadUserSid` at `0x1800181c4`
- `mqsec!MQSec_GetUserType` at `0x180018191`
- `mqsec!MQSec_GetUserType` at `0x180018191`

## pseudocode

```c
__int64 __fastcall RTpGetThreadUserSid(int *a1, int *a2, unsigned __int8 **a3, unsigned int *a4)
{
  int UserType; // eax
  unsigned int v9; // ebx
  unsigned __int16 v10; // r8
  int v11; // ecx
  int ThreadUserSid; // eax
  unsigned __int8 *LocalMachineSid; // rax
  int v15[14]; // [rsp+20h] [rbp-38h] BYREF

  v15[0] = 0;
  UserType = MQSec_GetUserType(0, a1, a2, v15);
  v9 = UserType;
  if ( UserType < 0 )
  {
    v10 = 60;
    v11 = UserType;
LABEL_8:
    LogMsgHR(v11, (wchar_t *)L"rt/rtutil", v10);
    return v9;
  }
  if ( *a2 || v15[0] )
  {
    LocalMachineSid = (unsigned __int8 *)MQSec_GetLocalMachineSid(1, a4);
    *a3 = LocalMachineSid;
    if ( !LocalMachineSid )
    {
      *a4 = 0;
      *a2 = 0;
      if ( a1 )
        *a1 = 1;
    }
  }
  else if ( !*a1 )
  {
    ThreadUserSid = MQSec_GetThreadUserSid(0, (void **)a3, a4, 0);
    v9 = ThreadUserSid;
    if ( ThreadUserSid < 0 )
    {
      v10 = 70;
      v11 = ThreadUserSid;
      goto LABEL_8;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180018164  push    rbx
0x180018166  push    rsi
0x180018167  push    rdi
0x180018168  push    r14
0x18001816a  push    r15
0x18001816c  sub     rsp, 30h
0x180018170  mov     r15, r8
0x180018173  mov     [rsp+58h+var_38], 0
0x18001817b  mov     r8, rdx
0x18001817e  mov     r14, rdx
0x180018181  mov     rdx, rcx
0x180018184  mov     rsi, r9
0x180018187  mov     rdi, rcx
0x18001818a  lea     r9, [rsp+58h+var_38]
0x18001818f  xor     ecx, ecx
0x180018191  call    cs:__imp_?MQSec_GetUserType@@YAJPEAXPEAH11@Z; MQSec_GetUserType(void *,int *,int *,int *)
0x180018197  mov     ebx, eax
0x180018199  test    eax, eax
0x18001819b  jns     short loc_1800181A7
0x18001819d  mov     r8d, 3Ch ; '<'
0x1800181a3  mov     ecx, eax
0x1800181a5  jmp     short loc_1800181D8
0x1800181a7  cmp     dword ptr [r14], 0
0x1800181ab  jnz     short loc_1800181E6
0x1800181ad  cmp     [rsp+58h+var_38], 0
0x1800181b2  jnz     short loc_1800181E6
0x1800181b4  cmp     dword ptr [rdi], 0
0x1800181b7  jnz     short loc_18001820C
0x1800181b9  xor     r9d, r9d
0x1800181bc  mov     r8, rsi
0x1800181bf  mov     rdx, r15
0x1800181c2  xor     ecx, ecx
0x1800181c4  call    cs:__imp_?MQSec_GetThreadUserSid@@YAJHPEAPEAXPEAKH@Z; MQSec_GetThreadUserSid(int,void * *,ulong *,int)
0x1800181ca  mov     ebx, eax
0x1800181cc  test    eax, eax
0x1800181ce  jns     short loc_18001820C
0x1800181d0  mov     r8d, 46h ; 'F'; unsigned __int16
0x1800181d6  mov     ecx, eax; int
0x1800181d8  lea     rdx, aRtRtutil; "rt/rtutil"
0x1800181df  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800181e4  jmp     short loc_18001820C
0x1800181e6  mov     rdx, rsi
0x1800181e9  mov     ecx, 1
0x1800181ee  call    cs:__imp_?MQSec_GetLocalMachineSid@@YAPEAXHPEAK@Z; MQSec_GetLocalMachineSid(int,ulong *)
0x1800181f4  mov     [r15], rax
0x1800181f7  test    rax, rax
0x1800181fa  jnz     short loc_18001820C
0x1800181fc  mov     [rsi], eax
0x1800181fe  mov     [r14], eax
0x180018201  test    rdi, rdi
0x180018204  jz      short loc_18001820C
0x180018206  mov     dword ptr [rdi], 1
0x18001820c  mov     eax, ebx
0x18001820e  add     rsp, 30h
0x180018212  pop     r15
0x180018214  pop     r14
0x180018216  pop     rdi
0x180018217  pop     rsi
0x180018218  pop     rbx
0x180018219  retn
```
