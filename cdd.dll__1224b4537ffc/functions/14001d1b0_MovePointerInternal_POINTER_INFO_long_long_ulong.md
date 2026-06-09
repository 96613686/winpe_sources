# MovePointerInternal(_POINTER_INFO *,long,long,ulong)

- ea: `0x14001d1b0`
- end: `0x14001d2f8`
- name: `?MovePointerInternal@@YAXPEAU_POINTER_INFO@@JJK@Z`
- size: `328`
- prototype: `void __fastcall(struct _POINTER_INFO *, int, int, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140021660`
- `0x1400359f0`
- `0x140035ee0`
- `0x140035fb0`

## callees

- `0x14001d1b0`
- `0x1400371f0`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x14001d24a`
- `watchdog!WdLogSingleEntry2` at `0x14001d2e2`
- `watchdog!WdLogSingleEntry2` at `0x14001d24a`
- `watchdog!WdLogSingleEntry2` at `0x14001d2e2`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14001d261`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14001d261`

## pseudocode

```c
void __fastcall MovePointerInternal(struct _POINTER_INFO *a1, int a2, int a3, char a4)
{
  int v5; // r8d
  int v6; // edx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rcx
  int v10; // eax
  int v11; // ebx
  _QWORD *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rcx
  int v16; // eax
  int v17; // [rsp+20h] [rbp-28h] BYREF
  __int64 v18; // [rsp+24h] [rbp-24h]
  int v19; // [rsp+2Ch] [rbp-1Ch]

  if ( a3 >= 0 || a2 < 0 )
  {
    if ( a2 == -1 )
    {
      v13 = *(unsigned __int8 *)a1;
      v17 = *((_DWORD *)a1 + 8);
      v14 = *((_QWORD *)a1 + 12);
      v15 = *((_QWORD *)a1 + 13);
      v19 = 2 * (a4 & 1);
      v18 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, int *, __int64))(v14 + 136))(v15, &v17, v13);
      if ( v16 >= 0 )
        return;
      WdLogSingleEntry2(3, v16, *((_QWORD *)a1 + 13));
      v11 = 81;
    }
    else
    {
      if ( !*((_BYTE *)a1 + 12) )
        return;
      v5 = a3 - *((_DWORD *)a1 + 2);
      v6 = a2 - *((_DWORD *)a1 + 1);
      v17 = *((_DWORD *)a1 + 8);
      v7 = *((_QWORD *)a1 + 12);
      HIDWORD(v18) = v5;
      v8 = *(unsigned __int8 *)a1;
      v9 = *((_QWORD *)a1 + 13);
      LODWORD(v18) = v6;
      v19 = (2 * (a4 & 1)) | 1;
      v10 = (*(__int64 (__fastcall **)(__int64, int *, __int64))(v7 + 136))(v9, &v17, v8);
      if ( v10 >= 0 )
        return;
      WdLogSingleEntry2(3, v10, *((_QWORD *)a1 + 13));
      v11 = 102;
    }
    WdLogGlobalForLineNumber = v11;
    v12 = (_QWORD *)WdLogNewEntry5_WdWarning();
    v12[3] = gCddImageInfo;
    v12[4] = (unsigned int)dword_14003E570;
    v12[5] = 215857758;
    WdLogGlobalForLineNumber = v11;
  }
}

```

## disassembly

```asm
0x14001d1b0  push    rbx
0x14001d1b2  sub     rsp, 40h
0x14001d1b6  mov     rax, cs:__security_cookie
0x14001d1bd  xor     rax, rsp
0x14001d1c0  mov     [rsp+48h+var_18], rax
0x14001d1c5  mov     rbx, rcx
0x14001d1c8  test    r8d, r8d
0x14001d1cb  js      short loc_14001D1F0
0x14001d1cd  cmp     edx, 0FFFFFFFFh
0x14001d1d0  jz      loc_14001D295
0x14001d1d6  cmp     byte ptr [rcx+0Ch], 0
0x14001d1da  jnz     short loc_14001D1F6
0x14001d1dc  mov     rcx, [rsp+48h+var_18]
0x14001d1e1  xor     rcx, rsp; StackCookie
0x14001d1e4  call    __security_check_cookie
0x14001d1e9  add     rsp, 40h
0x14001d1ed  pop     rbx
0x14001d1ee  retn
0x14001d1f0  test    edx, edx
0x14001d1f2  js      short loc_14001D1CD
0x14001d1f4  jmp     short loc_14001D1DC
0x14001d1f6  mov     eax, [rcx+20h]
0x14001d1f9  and     r9d, 1
0x14001d1fd  sub     r8d, [rcx+8]
0x14001d201  add     r9d, r9d
0x14001d204  sub     edx, [rcx+4]
0x14001d207  or      r9d, 1
0x14001d20b  mov     [rsp+48h+var_28], eax
0x14001d20f  mov     rax, [rcx+60h]
0x14001d213  mov     dword ptr [rsp+48h+var_24+4], r8d
0x14001d218  movzx   r8d, byte ptr [rcx]
0x14001d21c  mov     rcx, [rcx+68h]
0x14001d220  mov     dword ptr [rsp+48h+var_24], edx
0x14001d224  lea     rdx, [rsp+48h+var_28]
0x14001d229  mov     [rsp+48h+var_1C], r9d
0x14001d22e  mov     rax, [rax+88h]
0x14001d235  call    _guard_dispatch_icall
0x14001d23a  test    eax, eax
0x14001d23c  jns     short loc_14001D1DC
0x14001d23e  mov     r8, [rbx+68h]
0x14001d242  mov     ecx, 3
0x14001d247  movsxd  rdx, eax
0x14001d24a  call    cs:__imp_WdLogSingleEntry2
0x14001d251  nop     dword ptr [rax+rax+00h]
0x14001d256  mov     ebx, 66h ; 'f'
0x14001d25b  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001d261  call    cs:__imp_WdLogNewEntry5_WdWarning
0x14001d268  nop     dword ptr [rax+rax+00h]
0x14001d26d  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001d274  mov     [rax+18h], rcx
0x14001d278  mov     ecx, cs:dword_14003E570
0x14001d27e  mov     [rax+20h], rcx
0x14001d282  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001d28a  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001d290  jmp     loc_14001D1DC
0x14001d295  mov     eax, [rcx+20h]
0x14001d298  lea     rdx, [rsp+48h+var_28]
0x14001d29d  movzx   r8d, byte ptr [rcx]
0x14001d2a1  and     r9d, 1
0x14001d2a5  mov     [rsp+48h+var_28], eax
0x14001d2a9  add     r9d, r9d
0x14001d2ac  mov     rax, [rcx+60h]
0x14001d2b0  mov     rcx, [rcx+68h]
0x14001d2b4  mov     [rsp+48h+var_1C], r9d
0x14001d2b9  mov     [rsp+48h+var_24], 0
0x14001d2c2  mov     rax, [rax+88h]
0x14001d2c9  call    _guard_dispatch_icall
0x14001d2ce  test    eax, eax
0x14001d2d0  jns     loc_14001D1DC
0x14001d2d6  mov     r8, [rbx+68h]
0x14001d2da  mov     ecx, 3
0x14001d2df  movsxd  rdx, eax
0x14001d2e2  call    cs:__imp_WdLogSingleEntry2
0x14001d2e9  nop     dword ptr [rax+rax+00h]
0x14001d2ee  mov     ebx, 51h ; 'Q'
0x14001d2f3  jmp     loc_14001D25B
```
