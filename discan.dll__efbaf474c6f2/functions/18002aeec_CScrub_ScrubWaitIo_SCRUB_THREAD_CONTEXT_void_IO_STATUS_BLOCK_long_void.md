# CScrub::_ScrubWaitIo(_SCRUB_THREAD_CONTEXT *,void *,_IO_STATUS_BLOCK *,long,void *)

- ea: `0x18002aeec`
- end: `0x18002b134`
- name: `?_ScrubWaitIo@CScrub@@AEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXPEAU_IO_STATUS_BLOCK@@J1@Z`
- size: `584`
- prototype: `int __fastcall(CScrub *this, struct _SCRUB_THREAD_CONTEXT *, void *, struct _IO_STATUS_BLOCK *, int, HANDLE Handle)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180022450`
- `0x18002892c`

## callees

- `0x18001fc04`
- `0x18002aeec`
- `0x18002c6f8`
- `0x180037620`

## import_xrefs

- `ntdll!NtCancelIoFileEx` at `0x18002afe5`
- `ntdll!NtCancelIoFileEx` at `0x18002b087`
- `ntdll!NtCancelIoFileEx` at `0x18002afe5`
- `ntdll!NtCancelIoFileEx` at `0x18002b087`
- `ntdll!NtWaitForMultipleObjects` at `0x18002af73`
- `ntdll!NtWaitForMultipleObjects` at `0x18002af73`
- `ntdll!NtWaitForSingleObject` at `0x18002b0eb`
- `ntdll!NtWaitForSingleObject` at `0x18002b0eb`

## pseudocode

```c
int __fastcall CScrub::_ScrubWaitIo(
        CScrub *this,
        struct _SCRUB_THREAD_CONTEXT *a2,
        void *a3,
        struct _IO_STATUS_BLOCK *a4,
        int a5,
        HANDLE Handle)
{
  union _LARGE_INTEGER *Time; // rax
  NTSTATUS v11; // ecx
  char v12; // r10
  _QWORD *v13; // rcx
  int v14; // edx
  int result; // eax
  __int128 v16; // [rsp+40h] [rbp-68h] BYREF
  HANDLE Object[3]; // [rsp+50h] [rbp-58h] BYREF

  if ( a5 != 259 )
    Handle = (HANDLE)*((_QWORD *)this + 150);
  Object[0] = *((HANDLE *)this + 2);
  Object[1] = *((HANDLE *)this + 152);
  Time = 0;
  Object[2] = Handle;
  if ( a5 != 259 )
    Time = &LiZero;
  v11 = NtWaitForMultipleObjects(3u, Object, WaitAny, 0, Time);
  switch ( v11 )
  {
    case 0:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          172,
          (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
          *(_DWORD *)(**(_QWORD **)this + 16LL),
          *(_DWORD *)(**(_QWORD **)this + 36LL),
          *(_QWORD *)(*(_QWORD *)this + 64LL));
      }
      v16 = 0;
      v12 = NtCancelIoFileEx(a3, a4, &v16);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_24;
      }
      v14 = 173;
LABEL_23:
      WPP_SF_DDZdd(
        v13[2],
        v14,
        *(_QWORD *)this,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        v12,
        v16);
LABEL_24:
      if ( a5 == 259 )
        NtWaitForSingleObject(Handle, 0, 0);
      return -805306102;
    case 1:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          174,
          (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
          *(_DWORD *)(**(_QWORD **)this + 16LL),
          *(_DWORD *)(**(_QWORD **)this + 36LL),
          *(_QWORD *)(*(_QWORD *)this + 64LL));
      }
      v16 = 0;
      v12 = NtCancelIoFileEx(a3, a4, &v16);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_24;
      }
      v14 = 175;
      goto LABEL_23;
    case 2:
      return a4->Status | 0x10000000;
  }
  result = -2147467259;
  if ( v11 == 258 )
    return a5 | 0x10000000;
  return result;
}

```

## disassembly

```asm
0x18002aeec  push    rbx
0x18002aeee  push    rbp
0x18002aeef  push    rsi
0x18002aef0  push    rdi
0x18002aef1  push    r13
0x18002aef3  push    r14
0x18002aef5  push    r15
0x18002aef7  sub     rsp, 70h
0x18002aefb  mov     rax, cs:__security_cookie
0x18002af02  xor     rax, rsp
0x18002af05  mov     [rsp+0A8h+var_40], rax
0x18002af0a  mov     ebx, [rsp+0A8h+arg_20]
0x18002af11  mov     r13d, 103h
0x18002af17  mov     rbp, [rsp+0A8h+Handle]
0x18002af1f  mov     r14, r9
0x18002af22  mov     r15, r8
0x18002af25  mov     rsi, rcx
0x18002af28  cmp     ebx, r13d
0x18002af2b  jz      short loc_18002AF34
0x18002af2d  mov     rbp, [rcx+4B0h]
0x18002af34  mov     rax, [rcx+10h]
0x18002af38  lea     rdx, [rsp+0A8h+Object]; Object
0x18002af3d  mov     [rsp+0A8h+Object], rax
0x18002af42  mov     rax, [rcx+4C0h]
0x18002af49  lea     rcx, ?LiZero@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER LiZero
0x18002af50  mov     [rsp+0A8h+var_50], rax
0x18002af55  xor     eax, eax
0x18002af57  cmp     ebx, r13d
0x18002af5a  mov     [rsp+0A8h+var_48], rbp
0x18002af5f  cmovnz  rax, rcx
0x18002af63  xor     r9d, r9d; Alertable
0x18002af66  mov     [rsp+0A8h+Time], rax; Time
0x18002af6b  lea     r8d, [r9+1]; WaitType
0x18002af6f  lea     ecx, [r9+3]; Count
0x18002af73  call    cs:__imp_NtWaitForMultipleObjects
0x18002af79  mov     ecx, eax
0x18002af7b  test    eax, eax
0x18002af7d  jnz     loc_18002B01C
0x18002af83  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af8a  lea     rdi, WPP_GLOBAL_Control
0x18002af91  cmp     rcx, rdi
0x18002af94  jz      short loc_18002AFD2
0x18002af96  test    byte ptr [rcx+1Ch], 1
0x18002af9a  jz      short loc_18002AFD2
0x18002af9c  cmp     byte ptr [rcx+19h], 4
0x18002afa0  jb      short loc_18002AFD2
0x18002afa2  mov     rax, [rsi]
0x18002afa5  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x18002afac  mov     rcx, [rcx+10h]
0x18002afb0  mov     edx, 0ACh
0x18002afb5  mov     r9, [rax]
0x18002afb8  mov     rax, [rax+40h]
0x18002afbc  mov     [rsp+0A8h+var_80], rax
0x18002afc1  mov     eax, [r9+24h]
0x18002afc5  mov     r9d, [r9+10h]
0x18002afc9  mov     dword ptr [rsp+0A8h+Time], eax
0x18002afcd  call    WPP_SF_DDZ
0x18002afd2  xorps   xmm0, xmm0
0x18002afd5  lea     r8, [rsp+0A8h+var_68]
0x18002afda  mov     rdx, r14
0x18002afdd  mov     rcx, r15
0x18002afe0  movups  [rsp+0A8h+var_68], xmm0
0x18002afe5  call    cs:__imp_NtCancelIoFileEx
0x18002afeb  mov     r10d, eax
0x18002afee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aff5  cmp     rcx, rdi
0x18002aff8  jz      loc_18002B0DE
0x18002affe  test    byte ptr [rcx+1Ch], 1
0x18002b002  jz      loc_18002B0DE
0x18002b008  cmp     byte ptr [rcx+19h], 4
0x18002b00c  jb      loc_18002B0DE
0x18002b012  mov     edx, 0ADh
0x18002b017  jmp     loc_18002B0AD
0x18002b01c  cmp     ecx, 1
0x18002b01f  jnz     loc_18002B0F8
0x18002b025  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b02c  lea     rdi, WPP_GLOBAL_Control
0x18002b033  cmp     rcx, rdi
0x18002b036  jz      short loc_18002B074
0x18002b038  test    byte ptr [rcx+1Ch], 1
0x18002b03c  jz      short loc_18002B074
0x18002b03e  cmp     byte ptr [rcx+19h], 4
0x18002b042  jb      short loc_18002B074
0x18002b044  mov     rax, [rsi]
0x18002b047  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x18002b04e  mov     rcx, [rcx+10h]
0x18002b052  mov     edx, 0AEh
0x18002b057  mov     r9, [rax]
0x18002b05a  mov     rax, [rax+40h]
0x18002b05e  mov     [rsp+0A8h+var_80], rax
0x18002b063  mov     eax, [r9+24h]
0x18002b067  mov     r9d, [r9+10h]
0x18002b06b  mov     dword ptr [rsp+0A8h+Time], eax
0x18002b06f  call    WPP_SF_DDZ
0x18002b074  xorps   xmm0, xmm0
0x18002b077  lea     r8, [rsp+0A8h+var_68]
0x18002b07c  mov     rdx, r14
0x18002b07f  mov     rcx, r15
0x18002b082  movups  [rsp+0A8h+var_68], xmm0
0x18002b087  call    cs:__imp_NtCancelIoFileEx
0x18002b08d  mov     r10d, eax
0x18002b090  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b097  cmp     rcx, rdi
0x18002b09a  jz      short loc_18002B0DE
0x18002b09c  test    byte ptr [rcx+1Ch], 1
0x18002b0a0  jz      short loc_18002B0DE
0x18002b0a2  cmp     byte ptr [rcx+19h], 4
0x18002b0a6  jb      short loc_18002B0DE
0x18002b0a8  mov     edx, 0AFh
0x18002b0ad  mov     r8, [rsi]
0x18002b0b0  mov     eax, dword ptr [rsp+0A8h+var_68]
0x18002b0b4  mov     rcx, [rcx+10h]
0x18002b0b8  mov     [rsp+0A8h+var_70], eax
0x18002b0bc  mov     r9, [r8]
0x18002b0bf  mov     rax, [r8+40h]
0x18002b0c3  mov     [rsp+0A8h+var_78], r10d
0x18002b0c8  mov     [rsp+0A8h+var_80], rax
0x18002b0cd  mov     eax, [r9+24h]
0x18002b0d1  mov     r9d, [r9+10h]
0x18002b0d5  mov     dword ptr [rsp+0A8h+Time], eax
0x18002b0d9  call    WPP_SF_DDZdd
0x18002b0de  cmp     ebx, r13d
0x18002b0e1  jnz     short loc_18002B0F1
0x18002b0e3  xor     r8d, r8d; Timeout
0x18002b0e6  xor     edx, edx; Alertable
0x18002b0e8  mov     rcx, rbp; Handle
0x18002b0eb  call    cs:__imp_NtWaitForSingleObject
0x18002b0f1  mov     eax, 0D000010Ah
0x18002b0f6  jmp     short loc_18002B118
0x18002b0f8  cmp     ecx, 2
0x18002b0fb  jnz     short loc_18002B106
0x18002b0fd  mov     eax, [r14]
0x18002b100  bts     eax, 1Ch
0x18002b104  jmp     short loc_18002B118
0x18002b106  bts     ebx, 1Ch
0x18002b10a  mov     eax, 80004005h
0x18002b10f  cmp     ecx, 102h
0x18002b115  cmovz   eax, ebx
0x18002b118  mov     rcx, [rsp+0A8h+var_40]
0x18002b11d  xor     rcx, rsp; StackCookie
0x18002b120  call    __security_check_cookie
0x18002b125  add     rsp, 70h
0x18002b129  pop     r15
0x18002b12b  pop     r14
0x18002b12d  pop     r13
0x18002b12f  pop     rdi
0x18002b130  pop     rsi
0x18002b131  pop     rbp
0x18002b132  pop     rbx
0x18002b133  retn
```
