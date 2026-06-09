# KpsReadMitRealms(ulong (*)(_UNICODE_STRING *,_KPS_MIT_REALM *))

- ea: `0x18002ea8c`
- end: `0x18002eb4a`
- name: `?KpsReadMitRealms@@YAKP6AKPEAU_UNICODE_STRING@@PEAU_KPS_MIT_REALM@@@Z@Z`
- size: `190`
- prototype: `__int64 __fastcall(unsigned int (*)(struct _UNICODE_STRING *, struct _KPS_MIT_REALM *))`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180029e64`

## callees

- `0x18001ae0c`
- `0x18001ae38`
- `0x18002ea8c`
- `0x18002eb50`

## pseudocode

```c
__int64 __fastcall KpsReadMitRealms(unsigned int (*a1)(struct _UNICODE_STRING *, struct _KPS_MIT_REALM *))
{
  unsigned int (*v1)(struct _UNICODE_STRING *, struct _KPS_MIT_REALM *); // rcx
  unsigned int (*v2)(struct _UNICODE_STRING *, struct _KPS_MIT_REALM *); // rcx
  unsigned int MitRealmsFromRegistry; // ebx
  _QWORD *v4; // rcx

  v1 = (unsigned int (*)(struct _UNICODE_STRING *, struct _KPS_MIT_REALM *))WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids);
  MitRealmsFromRegistry = KpsReadMitRealmsFromRegistry(v1, 1u);
  if ( MitRealmsFromRegistry == 2 )
  {
    MitRealmsFromRegistry = KpsReadMitRealmsFromRegistry(v2, 0);
    if ( MitRealmsFromRegistry == 2 )
    {
      MitRealmsFromRegistry = 0;
LABEL_11:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_12;
    }
  }
  if ( !MitRealmsFromRegistry )
    goto LABEL_11;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return MitRealmsFromRegistry;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      58,
      &WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids,
      MitRealmsFromRegistry);
    goto LABEL_11;
  }
LABEL_12:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_D(v4[2], 59, &WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids, MitRealmsFromRegistry);
  return MitRealmsFromRegistry;
}

```

## disassembly

```asm
0x18002ea8c  mov     [rsp+arg_0], rbx
0x18002ea91  push    rdi
0x18002ea92  sub     rsp, 20h
0x18002ea96  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea9d  lea     rdi, WPP_GLOBAL_Control
0x18002eaa4  cmp     rcx, rdi
0x18002eaa7  jz      short loc_18002EAC4
0x18002eaa9  test    byte ptr [rcx+1Ch], 20h
0x18002eaad  jz      short loc_18002EAC4
0x18002eaaf  mov     rcx, [rcx+10h]
0x18002eab3  lea     r8, WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids
0x18002eaba  mov     edx, 39h ; '9'
0x18002eabf  call    WPP_SF_
0x18002eac4  mov     dl, 1; unsigned __int8
0x18002eac6  call    ?KpsReadMitRealmsFromRegistry@@YAKP6AKPEAU_UNICODE_STRING@@PEAU_KPS_MIT_REALM@@@ZE@Z; KpsReadMitRealmsFromRegistry(ulong (*)(_UNICODE_STRING *,_KPS_MIT_REALM *),uchar)
0x18002eacb  mov     ebx, eax
0x18002eacd  cmp     eax, 2
0x18002ead0  jnz     short loc_18002EAE4
0x18002ead2  xor     edx, edx; unsigned __int8
0x18002ead4  call    ?KpsReadMitRealmsFromRegistry@@YAKP6AKPEAU_UNICODE_STRING@@PEAU_KPS_MIT_REALM@@@ZE@Z; KpsReadMitRealmsFromRegistry(ulong (*)(_UNICODE_STRING *,_KPS_MIT_REALM *),uchar)
0x18002ead9  mov     ebx, eax
0x18002eadb  cmp     eax, 2
0x18002eade  jnz     short loc_18002EAE4
0x18002eae0  xor     ebx, ebx
0x18002eae2  jmp     short loc_18002EB12
0x18002eae4  test    ebx, ebx
0x18002eae6  jz      short loc_18002EB12
0x18002eae8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eaef  cmp     rcx, rdi
0x18002eaf2  jz      short loc_18002EB3C
0x18002eaf4  test    byte ptr [rcx+1Ch], 1
0x18002eaf8  jz      short loc_18002EB19
0x18002eafa  mov     rcx, [rcx+10h]
0x18002eafe  lea     r8, WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids
0x18002eb05  mov     edx, 3Ah ; ':'
0x18002eb0a  mov     r9d, ebx
0x18002eb0d  call    WPP_SF_D
0x18002eb12  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb19  cmp     rcx, rdi
0x18002eb1c  jz      short loc_18002EB3C
0x18002eb1e  test    byte ptr [rcx+1Ch], 20h
0x18002eb22  jz      short loc_18002EB3C
0x18002eb24  mov     rcx, [rcx+10h]
0x18002eb28  lea     r8, WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids
0x18002eb2f  mov     edx, 3Bh ; ';'
0x18002eb34  mov     r9d, ebx
0x18002eb37  call    WPP_SF_D
0x18002eb3c  mov     eax, ebx
0x18002eb3e  mov     rbx, [rsp+28h+arg_0]
0x18002eb43  add     rsp, 20h
0x18002eb47  pop     rdi
0x18002eb48  retn
```
