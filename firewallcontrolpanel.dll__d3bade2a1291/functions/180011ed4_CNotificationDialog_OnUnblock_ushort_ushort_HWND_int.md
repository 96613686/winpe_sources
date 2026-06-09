# CNotificationDialog::OnUnblock(ushort,ushort,HWND__ *,int &)

- ea: `0x180011ed4`
- end: `0x18001201b`
- name: `?OnUnblock@CNotificationDialog@@AEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `327`
- prototype: `__int64 __fastcall(CNotificationDialog *__hidden this, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180012270`

## callees

- `0x180011ed4`
- `0x180013e3c`
- `0x180015a7c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180011fa3`
- `ntdll!EtwEventWrite` at `0x180011ff1`
- `ntdll!EtwEventWrite` at `0x180011fa3`
- `ntdll!EtwEventWrite` at `0x180011ff1`
- `USER32!EndDialog` at `0x180012005`
- `USER32!EndDialog` at `0x180012005`
- `USER32!IsDlgButtonChecked` at `0x180011f44`
- `USER32!IsDlgButtonChecked` at `0x180011f44`

## pseudocode

```c
__int64 __fastcall CNotificationDialog::OnUnblock(CNotificationDialog *this, __int64 a2, __int64 a3, HWND a4, int *a5)
{
  int v6; // r8d
  int v7; // ebp
  unsigned int v8; // edi
  int v9; // eax
  unsigned int v10; // esi
  int v11; // edi
  int v12; // edi
  int v14; // [rsp+28h] [rbp-60h]
  int nIDButton; // [rsp+40h] [rbp-48h]
  _DWORD v16[17]; // [rsp+44h] [rbp-44h]

  v6 = *((_DWORD *)this + 423);
  *a5 = 1;
  RecordSQMDataPointQueryUser((const unsigned __int16 *)this + 52, 1, v6);
  v7 = 0;
  nIDButton = 1617;
  v8 = 0;
  v16[0] = 4;
  v16[1] = 1618;
  v16[2] = 2;
  v16[3] = 1619;
  v16[4] = 1;
  do
  {
    if ( IsDlgButtonChecked(*((HWND *)this + 1), v16[2 * v8 - 1]) == 1 )
    {
      v9 = v16[2 * v8];
      if ( (v9 & *((_DWORD *)this + 416)) != 0 )
        v7 |= v9;
    }
    ++v8;
  }
  while ( v8 < 3 );
  v10 = v7 & ~(*((_DWORD *)this + 426) | *((_DWORD *)this + 427));
  if ( !v10 )
    goto LABEL_12;
  v11 = ~(*((_DWORD *)this + 426) | *((_DWORD *)this + 427)) & ~v10 & *((_DWORD *)this + 416);
  if ( g_Provider )
    EtwEventWrite(g_Provider, QUUnblock_Start, 0, 0);
  v12 = AllowApplication(
          *((HWND *)this + 1),
          (const unsigned __int16 *)this + 52,
          v10,
          *((_DWORD *)this + 418) | (unsigned int)v11,
          *((_DWORD *)this + 423),
          v14,
          *((_DWORD *)this + 429));
  if ( g_Provider )
    EtwEventWrite(g_Provider, QUUnblock_End, 0, 0);
  if ( v12 != -2147023673 )
LABEL_12:
    EndDialog(*((HWND *)this + 1), 0);
  return 1;
}

```

## disassembly

```asm
0x180011ed4  push    rbx
0x180011ed6  push    rbp
0x180011ed7  push    rsi
0x180011ed8  push    rdi
0x180011ed9  push    r14
0x180011edb  sub     rsp, 60h
0x180011edf  mov     rax, [rsp+88h+arg_20]
0x180011ee7  mov     rbx, rcx
0x180011eea  mov     r8d, [rcx+69Ch]; int
0x180011ef1  mov     edx, 1; int
0x180011ef6  add     rcx, 68h ; 'h'; unsigned __int16 *
0x180011efa  mov     dword ptr [rax], 1
0x180011f00  call    ?RecordSQMDataPointQueryUser@@YAXPEBGHH@Z; RecordSQMDataPointQueryUser(ushort const *,int,int)
0x180011f05  xor     ebp, ebp
0x180011f07  mov     [rsp+88h+nIDButton], 651h
0x180011f0f  xor     edi, edi
0x180011f11  mov     [rsp+88h+var_44], 4
0x180011f19  mov     [rsp+88h+var_40], 652h
0x180011f21  mov     [rsp+88h+var_3C], 2
0x180011f29  mov     [rsp+88h+var_38], 653h
0x180011f31  mov     [rsp+88h+var_34], 1
0x180011f39  mov     rcx, [rbx+8]; hDlg
0x180011f3d  movsxd  rsi, edi
0x180011f40  mov     edx, [rsp+rsi*8+88h+nIDButton]; nIDButton
0x180011f44  call    cs:__imp_IsDlgButtonChecked
0x180011f4a  cmp     eax, 1
0x180011f4d  jnz     short loc_180011F5D
0x180011f4f  mov     eax, [rsp+rsi*8+88h+var_44]
0x180011f53  test    [rbx+680h], eax
0x180011f59  jz      short loc_180011F5D
0x180011f5b  or      ebp, eax
0x180011f5d  inc     edi
0x180011f5f  cmp     edi, 3
0x180011f62  jb      short loc_180011F39
0x180011f64  mov     ecx, [rbx+6ACh]
0x180011f6a  or      ecx, [rbx+6A8h]
0x180011f70  not     ecx
0x180011f72  mov     esi, ecx
0x180011f74  and     esi, ebp
0x180011f76  jz      loc_180011FFF
0x180011f7c  mov     edi, [rbx+680h]
0x180011f82  mov     eax, esi
0x180011f84  not     eax
0x180011f86  and     edi, eax
0x180011f88  and     edi, ecx
0x180011f8a  mov     rcx, cs:g_Provider
0x180011f91  test    rcx, rcx
0x180011f94  jz      short loc_180011FA9
0x180011f96  xor     r9d, r9d
0x180011f99  lea     rdx, QUUnblock_Start
0x180011fa0  xor     r8d, r8d
0x180011fa3  call    cs:__imp_EtwEventWrite
0x180011fa9  mov     eax, [rbx+6B4h]
0x180011faf  lea     rdx, [rbx+68h]; unsigned __int16 *
0x180011fb3  or      edi, [rbx+688h]
0x180011fb9  mov     r8d, esi; unsigned int
0x180011fbc  mov     rcx, [rbx+8]; HWND
0x180011fc0  mov     r9d, edi; unsigned int
0x180011fc3  mov     [rsp+88h+var_58], eax; unsigned int
0x180011fc7  mov     eax, [rbx+69Ch]
0x180011fcd  mov     [rsp+88h+var_68], eax; int
0x180011fd1  call    ?AllowApplication@@YAJPEAUHWND__@@PEBGKKHHK@Z; AllowApplication(HWND__ *,ushort const *,ulong,ulong,int,int,ulong)
0x180011fd6  mov     rcx, cs:g_Provider
0x180011fdd  mov     edi, eax
0x180011fdf  test    rcx, rcx
0x180011fe2  jz      short loc_180011FF7
0x180011fe4  xor     r9d, r9d
0x180011fe7  lea     rdx, QUUnblock_End
0x180011fee  xor     r8d, r8d
0x180011ff1  call    cs:__imp_EtwEventWrite
0x180011ff7  cmp     edi, 800704C7h
0x180011ffd  jz      short loc_18001200B
0x180011fff  mov     rcx, [rbx+8]; hDlg
0x180012003  xor     edx, edx; nResult
0x180012005  call    cs:__imp_EndDialog
0x18001200b  mov     eax, 1
0x180012010  add     rsp, 60h
0x180012014  pop     r14
0x180012016  pop     rdi
0x180012017  pop     rsi
0x180012018  pop     rbp
0x180012019  pop     rbx
0x18001201a  retn
```
