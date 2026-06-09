# LanguagePackDiskCleanupTraceProvider::UninstallLXP_(ushort const *)

- ea: `0x14000c2ac`
- end: `0x14000c364`
- name: `?UninstallLXP_@LanguagePackDiskCleanupTraceProvider@@QEAAXPEBG@Z`
- size: `184`
- prototype: `void __fastcall(LanguagePackDiskCleanupTraceProvider *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140003260`

## callees

- `0x140001b9c`
- `0x140002190`
- `0x140007eac`
- `0x14000c2ac`

## pseudocode

```c
void __fastcall LanguagePackDiskCleanupTraceProvider::UninstallLXP_(
        LanguagePackDiskCleanupTraceProvider *this,
        const unsigned __int16 *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  int v5; // eax
  _BYTE v6[32]; // [rsp+30h] [rbp-48h] BYREF
  const unsigned __int16 *v7; // [rsp+50h] [rbp-28h]
  int v8; // [rsp+58h] [rbp-20h]
  int v9; // [rsp+5Ch] [rbp-1Ch]

  v3 = *((_QWORD *)LanguagePackDiskCleanupTraceProvider::Instance() + 1);
  if ( *(_DWORD *)v3 > 5u
    && (*(_QWORD *)(v3 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v3 + 24) & 0x400000000000LL) == *(_QWORD *)(v3 + 24) )
  {
    if ( a2 )
    {
      v4 = -1;
      do
        ++v4;
      while ( a2[v4] );
      v5 = 2 * v4 + 2;
    }
    else
    {
      a2 = (const unsigned __int16 *)&dword_140013804;
      v5 = 2;
    }
    v7 = a2;
    v8 = v5;
    v9 = 0;
    tlgWriteTransfer_EventWriteTransfer(v3, qword_140014758, 0, 0, 3, v6);
  }
}

```

## disassembly

```asm
0x14000c2ac  push    rbx
0x14000c2ae  sub     rsp, 70h
0x14000c2b2  mov     rax, cs:__security_cookie
0x14000c2b9  xor     rax, rsp
0x14000c2bc  mov     [rsp+78h+var_18], rax
0x14000c2c1  mov     rbx, rdx
0x14000c2c4  call    ?Instance@LanguagePackDiskCleanupTraceProvider@@KAPEAV1@XZ; LanguagePackDiskCleanupTraceProvider::Instance(void)
0x14000c2c9  mov     rcx, [rax+8]
0x14000c2cd  mov     eax, [rcx]
0x14000c2cf  cmp     eax, 5
0x14000c2d2  jbe     short loc_14000C351
0x14000c2d4  mov     rdx, [rcx+18h]
0x14000c2d8  mov     rax, [rcx+10h]
0x14000c2dc  mov     r8, 400000000000h
0x14000c2e6  test    r8, rax
0x14000c2e9  jz      short loc_14000C351
0x14000c2eb  mov     rax, rdx
0x14000c2ee  and     rax, r8
0x14000c2f1  cmp     rax, rdx
0x14000c2f4  jnz     short loc_14000C351
0x14000c2f6  xor     edx, edx
0x14000c2f8  test    rbx, rbx
0x14000c2fb  jz      short loc_14000C313
0x14000c2fd  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c301  inc     rax
0x14000c304  cmp     [rbx+rax*2], dx
0x14000c308  jnz     short loc_14000C301
0x14000c30a  lea     eax, ds:2[rax*2]
0x14000c311  jmp     short loc_14000C31F
0x14000c313  lea     rbx, dword_140013804
0x14000c31a  mov     eax, 2
0x14000c31f  mov     [rsp+78h+var_28], rbx
0x14000c324  mov     [rsp+78h+var_20], eax
0x14000c328  mov     [rsp+78h+var_1C], edx
0x14000c32c  lea     rax, [rsp+78h+var_48]
0x14000c331  mov     [rsp+78h+var_50], rax
0x14000c336  mov     [rsp+78h+var_58], 3
0x14000c33e  xor     r9d, r9d
0x14000c341  xor     r8d, r8d
0x14000c344  lea     rdx, qword_140014758
0x14000c34b  call    _tlgWriteTransfer_EventWriteTransfer
0x14000c350  nop
0x14000c351  mov     rcx, [rsp+78h+var_18]
0x14000c356  xor     rcx, rsp; StackCookie
0x14000c359  call    __security_check_cookie
0x14000c35e  add     rsp, 70h
0x14000c362  pop     rbx
0x14000c363  retn
```
