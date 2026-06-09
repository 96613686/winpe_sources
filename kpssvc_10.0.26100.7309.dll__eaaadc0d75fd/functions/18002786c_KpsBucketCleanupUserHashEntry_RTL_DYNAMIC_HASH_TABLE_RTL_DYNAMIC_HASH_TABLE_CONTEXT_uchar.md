# KpsBucketCleanupUserHashEntry(_RTL_DYNAMIC_HASH_TABLE *,_RTL_DYNAMIC_HASH_TABLE_CONTEXT *,uchar)

- ea: `0x18002786c`
- end: `0x1800279f0`
- name: `?KpsBucketCleanupUserHashEntry@@YAXPEAU_RTL_DYNAMIC_HASH_TABLE@@PEAU_RTL_DYNAMIC_HASH_TABLE_CONTEXT@@E@Z`
- size: `388`
- prototype: `void __fastcall(struct _RTL_DYNAMIC_HASH_TABLE *, struct _KPS_USER_HASH_ENTRY ***, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800276c8`
- `0x18002a2b8`

## callees

- `0x18001ae0c`
- `0x18001b1a0`
- `0x18002786c`
- `0x180028e1c`
- `0x18002a838`
- `0x18002c534`
- `0x18002c8d8`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18002797d`
- `ntdll!RtlRemoveEntryHashTable` at `0x18002797d`

## pseudocode

```c
void __fastcall KpsBucketCleanupUserHashEntry(
        struct _RTL_DYNAMIC_HASH_TABLE *a1,
        struct _KPS_USER_HASH_ENTRY ***a2,
        __int64 a3)
{
  char v3; // r14
  _QWORD *v6; // rcx
  unsigned __int64 v7; // r15
  struct _KPS_USER_HASH_ENTRY *v8; // rbx
  __int64 *v9; // rbp
  __int64 v10; // rdx
  __int64 v11; // r8

  v3 = a3;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a2);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)a1 + 7) )
  {
    v7 = (((unsigned __int64)MEMORY[0x7FFE0004] << 32) * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
    v8 = **a2;
    if ( v8 != (struct _KPS_USER_HASH_ENTRY *)*a2 )
    {
      do
      {
        v9 = *(__int64 **)v8;
        if ( *((_QWORD *)v8 + 8) && *((_QWORD *)v8 + 8) < v7
          || *((_QWORD *)v8 + 7) + (unsigned __int64)(unsigned int)(60000 * dword_18003A9B4) < v7 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_qZ(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v8 + 32);
          }
          RtlRemoveEntryHashTable(a1, v8, 0);
          KpsDereferenceUserHashEntry(v8, v10, v11);
          v3 = 1;
        }
        v8 = (struct _KPS_USER_HASH_ENTRY *)v9;
      }
      while ( v9 != (__int64 *)*a2 );
    }
    if ( v3 )
      KpsRebalanceHashTable(a1);
    goto LABEL_19;
  }
  if ( v6 == &WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)v6 + 28) & 8) != 0 )
  {
    WPP_SF_qd(v6[2], 19, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, a1, *((_DWORD *)a1 + 7));
LABEL_19:
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_(v6[2], 21, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids);
}

```

## disassembly

```asm
0x18002786c  mov     rax, rsp
0x18002786f  mov     [rax+8], rbx
0x180027873  mov     [rax+10h], rbp
0x180027877  mov     [rax+18h], rsi
0x18002787b  mov     [rax+20h], rdi
0x18002787f  push    r12
0x180027881  push    r14
0x180027883  push    r15
0x180027885  sub     rsp, 30h
0x180027889  mov     r14b, r8b
0x18002788c  mov     rsi, rdx
0x18002788f  mov     rdi, rcx
0x180027892  mov     rcx, cs:WPP_GLOBAL_Control
0x180027899  lea     r12, WPP_GLOBAL_Control
0x1800278a0  cmp     rcx, r12
0x1800278a3  jz      short loc_1800278C2
0x1800278a5  test    byte ptr [rcx+1Ch], 20h
0x1800278a9  jz      short loc_1800278C2
0x1800278ab  mov     rcx, [rcx+10h]
0x1800278af  mov     r9, rdi
0x1800278b2  mov     [rax-28h], rdx
0x1800278b6  call    WPP_SF_qq
0x1800278bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800278c2  mov     eax, [rdi+1Ch]
0x1800278c5  test    eax, eax
0x1800278c7  jz      short loc_1800278FD
0x1800278c9  cmp     rcx, r12
0x1800278cc  jz      loc_1800279D0
0x1800278d2  test    byte ptr [rcx+1Ch], 8
0x1800278d6  jz      loc_1800279B0
0x1800278dc  mov     rcx, [rcx+10h]
0x1800278e0  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x1800278e7  mov     edx, 13h
0x1800278ec  mov     dword ptr [rsp+48h+var_28], eax
0x1800278f0  mov     r9, rdi
0x1800278f3  call    WPP_SF_qd
0x1800278f8  jmp     loc_1800279A9
0x1800278fd  mov     ecx, ds:7FFE0004h
0x180027904  mov     eax, 7FFE0320h
0x180027909  shl     rcx, 20h
0x18002790d  mov     rax, [rax]
0x180027910  shl     rax, 8
0x180027914  mul     rcx
0x180027917  mov     rax, [rsi]
0x18002791a  mov     r15, rdx
0x18002791d  mov     rbx, [rax]
0x180027920  cmp     rbx, rax
0x180027923  jz      short loc_18002799C
0x180027925  cmp     qword ptr [rbx+40h], 0
0x18002792a  mov     rbp, [rbx]
0x18002792d  jz      short loc_180027935
0x18002792f  cmp     [rbx+40h], r15
0x180027933  jb      short loc_180027948
0x180027935  imul    ecx, cs:dword_18003A9B4, 0EA60h
0x18002793f  add     rcx, [rbx+38h]
0x180027943  cmp     rcx, r15
0x180027946  jnb     short loc_180027994
0x180027948  mov     rcx, cs:WPP_GLOBAL_Control
0x18002794f  cmp     rcx, r12
0x180027952  jz      short loc_180027974
0x180027954  test    byte ptr [rcx+1Ch], 40h
0x180027958  jz      short loc_180027974
0x18002795a  mov     rcx, [rcx+10h]; LoggerHandle
0x18002795e  lea     rax, [rbx+20h]
0x180027962  mov     edx, 14h
0x180027967  mov     [rsp+48h+var_28], rax; __int64
0x18002796c  mov     r9, rbx
0x18002796f  call    WPP_SF_qZ
0x180027974  xor     r8d, r8d
0x180027977  mov     rdx, rbx
0x18002797a  mov     rcx, rdi
0x18002797d  call    cs:__imp_RtlRemoveEntryHashTable
0x180027984  nop     dword ptr [rax+rax+00h]
0x180027989  mov     rcx, rbx; lpMem
0x18002798c  call    ?KpsDereferenceUserHashEntry@@YAXPEAU_KPS_USER_HASH_ENTRY@@@Z; KpsDereferenceUserHashEntry(_KPS_USER_HASH_ENTRY *)
0x180027991  mov     r14b, 1
0x180027994  mov     rbx, rbp
0x180027997  cmp     rbp, [rsi]
0x18002799a  jnz     short loc_180027925
0x18002799c  test    r14b, r14b
0x18002799f  jz      short loc_1800279A9
0x1800279a1  mov     rcx, rdi; struct _RTL_DYNAMIC_HASH_TABLE *
0x1800279a4  call    ?KpsRebalanceHashTable@@YAXPEAU_RTL_DYNAMIC_HASH_TABLE@@@Z; KpsRebalanceHashTable(_RTL_DYNAMIC_HASH_TABLE *)
0x1800279a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279b0  cmp     rcx, r12
0x1800279b3  jz      short loc_1800279D0
0x1800279b5  test    byte ptr [rcx+1Ch], 20h
0x1800279b9  jz      short loc_1800279D0
0x1800279bb  mov     rcx, [rcx+10h]
0x1800279bf  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x1800279c6  mov     edx, 15h
0x1800279cb  call    WPP_SF_
0x1800279d0  mov     rbx, [rsp+48h+arg_0]
0x1800279d5  mov     rbp, [rsp+48h+arg_8]
0x1800279da  mov     rsi, [rsp+48h+arg_10]
0x1800279df  mov     rdi, [rsp+48h+arg_18]
0x1800279e4  add     rsp, 30h
0x1800279e8  pop     r15
0x1800279ea  pop     r14
0x1800279ec  pop     r12
0x1800279ee  retn
```
