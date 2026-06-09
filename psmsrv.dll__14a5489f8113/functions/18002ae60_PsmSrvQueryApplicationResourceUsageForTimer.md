# PsmSrvQueryApplicationResourceUsageForTimer

- ea: `0x18002ae60`
- end: `0x18002afb9`
- name: `PsmSrvQueryApplicationResourceUsageForTimer`
- size: `345`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000772c`
- `0x180007bb0`
- `0x180008cc0`
- `0x180009b40`
- `0x18001622c`
- `0x18001c10c`
- `0x18002ae60`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002ae97`
- `ntdll!RtlLengthSid` at `0x18002ae97`
- `ntdll!RtlValidSid` at `0x18002aea8`
- `ntdll!RtlValidSid` at `0x18002aea8`

## pseudocode

```c
__int64 __fastcall PsmSrvQueryApplicationResourceUsageForTimer(
        __int64 a1,
        unsigned int a2,
        void *a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        int a8,
        _QWORD *a9)
{
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // [rsp+30h] [rbp-88h] BYREF
  _QWORD v16[15]; // [rsp+40h] [rbp-78h] BYREF

  v15 = 0;
  memset_0(v16, 0, 0x50u);
  if ( a2 >= 2 && RtlLengthSid(a3) == a2 && RtlValidSid(a3) )
  {
    if ( a9 )
    {
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)(a5 + 2 * v13) );
      if ( (int)PsmpFindApplicationByManagerForUser(a3, a4, a5, 2 * v13 + 2, a8, &v15) >= 0 )
      {
        PsmpQueryAppResourceUsage(v15, a6, a7, v16);
        v14 = v15;
        *a9 = v16[0];
        a9[1] = v16[1];
        PsmpDereferenceApplicationEx(v14, 0);
        return PsmpQueryVolumeIoTimes(a9);
      }
      else
      {
        return 3221225524LL;
      }
    }
    else
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
      return 3221225716LL;
    }
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
    return 3221225713LL;
  }
}

```

## disassembly

```asm
0x18002ae60  push    rbx
0x18002ae62  push    rbp
0x18002ae63  push    rsi
0x18002ae64  push    rdi
0x18002ae65  sub     rsp, 98h
0x18002ae6c  xor     ebp, ebp
0x18002ae6e  lea     rcx, [rsp+0B8h+var_78]; void *
0x18002ae73  mov     rdi, r8
0x18002ae76  mov     [rsp+0B8h+var_88], rbp
0x18002ae7b  mov     ebx, edx
0x18002ae7d  mov     esi, r9d
0x18002ae80  xor     edx, edx; Val
0x18002ae82  lea     r8d, [rbp+50h]; Size
0x18002ae86  call    memset_0
0x18002ae8b  cmp     ebx, 2
0x18002ae8e  jb      loc_18002AF80
0x18002ae94  mov     rcx, rdi; Sid
0x18002ae97  call    cs:__imp_RtlLengthSid
0x18002ae9d  cmp     eax, ebx
0x18002ae9f  jnz     loc_18002AF80
0x18002aea5  mov     rcx, rdi; Sid
0x18002aea8  call    cs:__imp_RtlValidSid
0x18002aeae  test    al, al
0x18002aeb0  jz      loc_18002AF80
0x18002aeb6  mov     rbx, [rsp+0B8h+arg_40]
0x18002aebe  test    rbx, rbx
0x18002aec1  jnz     short loc_18002AEF3
0x18002aec3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aeca  test    byte ptr [rcx+1Ch], 2
0x18002aece  jz      short loc_18002AEE9
0x18002aed0  cmp     byte ptr [rcx+19h], 2
0x18002aed4  jb      short loc_18002AEE9
0x18002aed6  mov     rcx, [rcx+10h]
0x18002aeda  lea     edx, [rbp+14h]
0x18002aedd  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002aee4  call    WPP_SF_
0x18002aee9  mov     eax, 0C00000F4h
0x18002aeee  jmp     loc_18002AFAD
0x18002aef3  mov     r8, [rsp+0B8h+arg_20]
0x18002aefb  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002aeff  inc     r9
0x18002af02  cmp     [r8+r9*2], bp
0x18002af07  jnz     short loc_18002AEFF
0x18002af09  lea     rax, [rsp+0B8h+var_88]
0x18002af0e  mov     edx, esi
0x18002af10  mov     [rsp+0B8h+var_90], rax; __int64
0x18002af15  lea     r9, ds:2[r9*2]
0x18002af1d  mov     eax, [rsp+0B8h+arg_38]
0x18002af24  mov     rcx, rdi; Sid2
0x18002af27  mov     [rsp+0B8h+var_98], eax; int
0x18002af2b  call    PsmpFindApplicationByManagerForUser
0x18002af30  test    eax, eax
0x18002af32  jns     short loc_18002AF3B
0x18002af34  mov     eax, 0C0000034h
0x18002af39  jmp     short loc_18002AFAD
0x18002af3b  mov     r8, [rsp+0B8h+arg_30]
0x18002af43  lea     r9, [rsp+0B8h+var_78]
0x18002af48  mov     edx, [rsp+0B8h+arg_28]
0x18002af4f  mov     rcx, [rsp+0B8h+var_88]
0x18002af54  call    PsmpQueryAppResourceUsage
0x18002af59  mov     rax, [rsp+0B8h+var_78]
0x18002af5e  xor     edx, edx
0x18002af60  mov     rcx, [rsp+0B8h+var_88]
0x18002af65  mov     [rbx], rax
0x18002af68  mov     rax, [rsp+0B8h+var_70]
0x18002af6d  mov     [rbx+8], rax
0x18002af71  call    PsmpDereferenceApplicationEx
0x18002af76  mov     rcx, rbx
0x18002af79  call    PsmpQueryVolumeIoTimes
0x18002af7e  jmp     short loc_18002AFAD
0x18002af80  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af87  test    byte ptr [rcx+1Ch], 2
0x18002af8b  jz      short loc_18002AFA8
0x18002af8d  cmp     byte ptr [rcx+19h], 2
0x18002af91  jb      short loc_18002AFA8
0x18002af93  mov     rcx, [rcx+10h]
0x18002af97  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002af9e  mov     edx, 13h
0x18002afa3  call    WPP_SF_
0x18002afa8  mov     eax, 0C00000F1h
0x18002afad  add     rsp, 98h
0x18002afb4  pop     rdi
0x18002afb5  pop     rsi
0x18002afb6  pop     rbp
0x18002afb7  pop     rbx
0x18002afb8  retn
```
