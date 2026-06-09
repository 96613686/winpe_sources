# PmDeleteProfile(_GUID *,ushort const *,ulong)

- ea: `0x18000c6ec`
- end: `0x18000c806`
- name: `?PmDeleteProfile@@YAKPEAU_GUID@@PEBGK@Z`
- size: `282`
- prototype: `__int64 __fastcall(struct _GUID *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001f704`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18000c6ec`
- `0x18000d638`
- `0x18000dae8`
- `0x18000dda4`
- `0x18000e240`
- `0x18000e43c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c751`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c751`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c7be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c7be`

## pseudocode

```c
__int64 __fastcall PmDeleteProfile(struct _GUID *a1, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned int KeyPcb; // ebx
  unsigned int v6; // r8d
  struct _PM_PCB_LIST *v7; // rdi
  __int64 v8; // rdx
  void *v9; // r8
  struct _PM_PCB_LIST *v11; // [rsp+38h] [rbp+10h] BYREF
  struct _PM_PCB *lpMem; // [rsp+48h] [rbp+20h] BYREF

  v11 = 0;
  lpMem = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 65, WPP_935883eb83d333df730e157613565e66_Traceguids);
  }
  EnterCriticalSection(&stru_180052D40);
  KeyPcb = PmpReferencePcbList(a1, a3, &v11);
  if ( !KeyPcb )
  {
    v6 = a3;
    v7 = v11;
    KeyPcb = PmpFindKeyPcb(v11, 0, v6, &lpMem);
    if ( !KeyPcb )
    {
      if ( *((struct _PM_PCB_LIST **)lpMem + 8) == v7 )
      {
        KeyPcb = PmpDeleteProfilePcb(lpMem, v8, v9);
        if ( !KeyPcb )
        {
          if ( (*((_BYTE *)v7 + 16) & 0x10) != 0 )
            PmpInvalidateVisibilityInterfacePcbLists();
          PmpNotifyProfileChangePcbList(v7);
        }
      }
      else
      {
        KeyPcb = 5;
      }
    }
  }
  LeaveCriticalSection(&stru_180052D40);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 66, WPP_935883eb83d333df730e157613565e66_Traceguids, KeyPcb);
  }
  return KeyPcb;
}

```

## disassembly

```asm
0x18000c6ec  mov     rax, rsp
0x18000c6ef  mov     [rax+8], rbx
0x18000c6f3  mov     [rax+18h], rsi
0x18000c6f7  mov     [rax+10h], rdx
0x18000c6fb  push    rdi
0x18000c6fc  sub     rsp, 20h
0x18000c700  mov     edi, r8d
0x18000c703  mov     qword ptr [rax+10h], 0
0x18000c70b  mov     rbx, rcx
0x18000c70e  mov     qword ptr [rax+20h], 0
0x18000c716  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c71d  lea     rsi, WPP_GLOBAL_Control
0x18000c724  cmp     rcx, rsi
0x18000c727  jz      short loc_18000C74A
0x18000c729  cmp     byte ptr [rcx+19h], 4
0x18000c72d  jb      short loc_18000C74A
0x18000c72f  test    byte ptr [rcx+1Ch], 1
0x18000c733  jz      short loc_18000C74A
0x18000c735  mov     rcx, [rcx+10h]
0x18000c739  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000c740  mov     edx, 41h ; 'A'
0x18000c745  call    WPP_SF_
0x18000c74a  lea     rcx, stru_180052D40; lpCriticalSection
0x18000c751  call    cs:__imp_EnterCriticalSection
0x18000c757  lea     r8, [rsp+28h+arg_8]; struct _PM_PCB_LIST **
0x18000c75c  mov     edx, edi; unsigned int
0x18000c75e  mov     rcx, rbx; struct _GUID *
0x18000c761  call    ?PmpReferencePcbList@@YAKPEAU_GUID@@KPEAPEAU_PM_PCB_LIST@@@Z; PmpReferencePcbList(_GUID *,ulong,_PM_PCB_LIST * *)
0x18000c766  mov     ebx, eax
0x18000c768  test    eax, eax
0x18000c76a  jnz     short loc_18000C7B7
0x18000c76c  mov     r8d, edi; unsigned int
0x18000c76f  lea     r9, [rsp+28h+lpMem]; struct _PM_PCB **
0x18000c774  mov     rdi, [rsp+28h+arg_8]
0x18000c779  xor     edx, edx; unsigned __int16 *
0x18000c77b  mov     rcx, rdi; struct _PM_PCB_LIST *
0x18000c77e  call    ?PmpFindKeyPcb@@YAKPEAU_PM_PCB_LIST@@PEBGKPEAPEAU_PM_PCB@@@Z; PmpFindKeyPcb(_PM_PCB_LIST *,ushort const *,ulong,_PM_PCB * *)
0x18000c783  mov     ebx, eax
0x18000c785  test    eax, eax
0x18000c787  jnz     short loc_18000C7B7
0x18000c789  mov     rcx, [rsp+28h+lpMem]; lpMem
0x18000c78e  cmp     [rcx+40h], rdi
0x18000c792  jz      short loc_18000C799
0x18000c794  lea     ebx, [rax+5]
0x18000c797  jmp     short loc_18000C7B7
0x18000c799  call    ?PmpDeleteProfilePcb@@YAKPEAU_PM_PCB@@@Z; PmpDeleteProfilePcb(_PM_PCB *)
0x18000c79e  mov     ebx, eax
0x18000c7a0  test    eax, eax
0x18000c7a2  jnz     short loc_18000C7B7
0x18000c7a4  test    byte ptr [rdi+10h], 10h
0x18000c7a8  jz      short loc_18000C7AF
0x18000c7aa  call    ?PmpInvalidateVisibilityInterfacePcbLists@@YAXXZ; PmpInvalidateVisibilityInterfacePcbLists(void)
0x18000c7af  mov     rcx, rdi; struct _PM_PCB_LIST *
0x18000c7b2  call    ?PmpNotifyProfileChangePcbList@@YAXPEAU_PM_PCB_LIST@@@Z; PmpNotifyProfileChangePcbList(_PM_PCB_LIST *)
0x18000c7b7  lea     rcx, stru_180052D40; lpCriticalSection
0x18000c7be  call    cs:__imp_LeaveCriticalSection
0x18000c7c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7cb  cmp     rcx, rsi
0x18000c7ce  jz      short loc_18000C7F4
0x18000c7d0  cmp     byte ptr [rcx+19h], 4
0x18000c7d4  jb      short loc_18000C7F4
0x18000c7d6  test    byte ptr [rcx+1Ch], 1
0x18000c7da  jz      short loc_18000C7F4
0x18000c7dc  mov     rcx, [rcx+10h]
0x18000c7e0  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000c7e7  mov     edx, 42h ; 'B'
0x18000c7ec  mov     r9d, ebx
0x18000c7ef  call    WPP_SF_d
0x18000c7f4  mov     rsi, [rsp+28h+arg_10]
0x18000c7f9  mov     eax, ebx
0x18000c7fb  mov     rbx, [rsp+28h+arg_0]
0x18000c800  add     rsp, 20h
0x18000c804  pop     rdi
0x18000c805  retn
```
