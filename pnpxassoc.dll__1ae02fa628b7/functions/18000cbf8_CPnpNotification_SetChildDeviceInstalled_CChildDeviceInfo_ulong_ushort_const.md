# CPnpNotification::SetChildDeviceInstalled(CChildDeviceInfo *,ulong,ushort const *)

- ea: `0x18000cbf8`
- end: `0x18000cce6`
- name: `?SetChildDeviceInstalled@CPnpNotification@@IEAAHPEAVCChildDeviceInfo@@KPEBG@Z`
- size: `238`
- prototype: `int(CPnpNotification *__hidden this, struct CChildDeviceInfo *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000c5a0`

## callees

- `0x18000bce4`
- `0x18000cbf8`
- `0x18000d4a4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000cc64`
- `msvcrt!_wcsicmp` at `0x18000cc64`

## pseudocode

```c
_BOOL8 __fastcall CPnpNotification::SetChildDeviceInstalled(
        CPnpNotification *this,
        const wchar_t **a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  BOOL v7; // ebx
  _QWORD *v8; // rax
  unsigned int v9; // esi

  v7 = 1;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  v9 = 0;
  if ( !a3 )
    goto LABEL_16;
  while ( 1 )
  {
    if ( _wcsicmp(a2[2 * v9 + 1], a4) )
      goto LABEL_8;
    if ( LODWORD(a2[2 * v9]) )
      break;
    LODWORD(a2[2 * v9]) = 1;
LABEL_8:
    v7 = v7 && LODWORD(a2[2 * v9]);
    if ( ++v9 >= a3 )
      goto LABEL_15;
  }
  v7 = 0;
LABEL_15:
  v8 = WPP_GLOBAL_Control;
LABEL_16:
  if ( v8 != &WPP_GLOBAL_Control && *((_BYTE *)v8 + 25) >= 4u )
    WPP_SF_sqP(v8[2], 45, &WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids);
  return v7;
}

```

## disassembly

```asm
0x18000cbf8  push    rbx
0x18000cbfa  push    rbp
0x18000cbfb  push    rsi
0x18000cbfc  push    rdi
0x18000cbfd  push    r12
0x18000cbff  push    r14
0x18000cc01  push    r15
0x18000cc03  sub     rsp, 30h
0x18000cc07  mov     r12, r9
0x18000cc0a  mov     r14d, r8d
0x18000cc0d  mov     rbp, rdx
0x18000cc10  mov     r15, rcx
0x18000cc13  mov     ebx, 1
0x18000cc18  mov     rax, cs:WPP_GLOBAL_Control
0x18000cc1f  lea     rcx, WPP_GLOBAL_Control
0x18000cc26  cmp     rax, rcx
0x18000cc29  jz      short loc_18000CC50
0x18000cc2b  cmp     byte ptr [rax+19h], 4
0x18000cc2f  jb      short loc_18000CC50
0x18000cc31  mov     rcx, [rax+10h]
0x18000cc35  lea     edx, [rbx+2Bh]
0x18000cc38  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000cc3f  mov     [rsp+68h+var_48], r15
0x18000cc44  call    WPP_SF_sq
0x18000cc49  mov     rax, cs:WPP_GLOBAL_Control
0x18000cc50  xor     esi, esi
0x18000cc52  test    r14d, r14d
0x18000cc55  jz      short loc_18000CCA2
0x18000cc57  mov     edi, esi
0x18000cc59  mov     rdx, r12; String2
0x18000cc5c  add     rdi, rdi
0x18000cc5f  mov     rcx, [rbp+rdi*8+8]; String1
0x18000cc64  call    cs:__imp__wcsicmp
0x18000cc6a  test    eax, eax
0x18000cc6c  jnz     short loc_18000CC7C
0x18000cc6e  cmp     [rbp+rdi*8+0], eax
0x18000cc72  jnz     short loc_18000CC99
0x18000cc74  mov     dword ptr [rbp+rdi*8+0], 1
0x18000cc7c  test    ebx, ebx
0x18000cc7e  jz      short loc_18000CC8E
0x18000cc80  cmp     dword ptr [rbp+rdi*8+0], 0
0x18000cc85  jz      short loc_18000CC8E
0x18000cc87  mov     ebx, 1
0x18000cc8c  jmp     short loc_18000CC90
0x18000cc8e  xor     ebx, ebx
0x18000cc90  inc     esi
0x18000cc92  cmp     esi, r14d
0x18000cc95  jb      short loc_18000CC57
0x18000cc97  jmp     short loc_18000CC9B
0x18000cc99  xor     ebx, ebx
0x18000cc9b  mov     rax, cs:WPP_GLOBAL_Control
0x18000cca2  lea     rcx, WPP_GLOBAL_Control
0x18000cca9  cmp     rax, rcx
0x18000ccac  jz      short loc_18000CCD5
0x18000ccae  cmp     byte ptr [rax+19h], 4
0x18000ccb2  jb      short loc_18000CCD5
0x18000ccb4  mov     ecx, ebx
0x18000ccb6  lea     r8, WPP_5470eb8e68d33996a7f3516ae832e086_Traceguids
0x18000ccbd  mov     [rsp+68h+var_40], rcx
0x18000ccc2  mov     edx, 2Dh ; '-'
0x18000ccc7  mov     rcx, [rax+10h]
0x18000cccb  mov     [rsp+68h+var_48], r15
0x18000ccd0  call    WPP_SF_sqP
0x18000ccd5  mov     eax, ebx
0x18000ccd7  add     rsp, 30h
0x18000ccdb  pop     r15
0x18000ccdd  pop     r14
0x18000ccdf  pop     r12
0x18000cce1  pop     rdi
0x18000cce2  pop     rsi
0x18000cce3  pop     rbp
0x18000cce4  pop     rbx
0x18000cce5  retn
```
