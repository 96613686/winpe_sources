# WriteSystemInfo(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *)

- ea: `0x18000e898`
- end: `0x18000ea4f`
- name: `?WriteSystemInfo@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _MINIDUMP_STREAM_INFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000c19c`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x18000bcbc`
- `0x18000e798`
- `0x18000e898`
- `0x18002c010`

## string_xrefs

- `0x18000e937`: `WriteSystemInfo.GetCpuInfo failed, 0x%08x`
- `0x18000e9be`: `WriteSystemInfo.GetOsCsdString failed, 0x%08x`

## pseudocode

```c
__int64 __fastcall WriteSystemInfo(struct _MINIDUMP_STATE *a1, struct _MINIDUMP_STREAM_INFO *a2)
{
  __int64 *v4; // rcx
  __int64 v5; // rax
  unsigned int v6; // esi
  const char *v7; // r8
  __int64 result; // rax
  __int64 v9; // rcx
  unsigned __int16 *v10; // rcx
  unsigned int v12; // edx
  unsigned int v13; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v14; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v15; // [rsp+58h] [rbp-A8h]
  __int128 v16; // [rsp+68h] [rbp-98h] BYREF
  __int64 v17; // [rsp+78h] [rbp-88h]
  unsigned __int16 v18[128]; // [rsp+80h] [rbp-80h] BYREF

  v17 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  memset_0(v18, 0, sizeof(v18));
  v4 = (__int64 *)*((_QWORD *)a1 + 2);
  v5 = *v4;
  v13 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, char *, char *, char *, __int128 *))(v5 + 24))(
         v4,
         &v14,
         (char *)&v14 + 2,
         (char *)&v14 + 4,
         (char *)&v14 + 6,
         &v16);
  if ( v6 )
  {
    v7 = "WriteSystemInfo.GetCpuInfo failed, 0x%08x";
LABEL_3:
    (*(void (__fastcall **)(_QWORD, __int64, const char *, _QWORD))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      4,
      v7,
      v6);
    return v6;
  }
  v9 = *((_QWORD *)a1 + 2);
  BYTE7(v14) = *((_BYTE *)a1 + 130);
  *((_QWORD *)&v14 + 1) = *((_QWORD *)a1 + 14);
  LODWORD(v15) = *((_DWORD *)a1 + 31);
  DWORD1(v15) = *((_DWORD *)a1 + 27);
  WORD6(v15) = *((_WORD *)a1 + 66);
  HIWORD(v15) = *((_WORD *)a1 + 64);
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64))(*(_QWORD *)v9 + 88LL))(v9, v18, 128);
  if ( v6 )
  {
    v7 = "WriteSystemInfo.GetOsCsdString failed, 0x%08x";
    goto LABEL_3;
  }
  v10 = v18;
  while ( *v10++ )
    ;
  if ( 2 * (unsigned int)(v10 - v18) != *((_DWORD *)a2 + 7) )
    return 2147942487LL;
  result = WriteStringToPool(a1, a2, v18, &v13);
  if ( !(_DWORD)result )
  {
    v12 = *((_DWORD *)a2 + 5);
    DWORD2(v15) = v13;
    return WriteAtOffset(a1, v12, &v14, 0x38u);
  }
  return result;
}

```

## disassembly

```asm
0x18000e898  mov     [rsp-8+arg_10], rbx
0x18000e89d  mov     [rsp-8+arg_18], rsi
0x18000e8a2  push    rbp
0x18000e8a3  push    rdi
0x18000e8a4  push    r14
0x18000e8a6  lea     rbp, [rsp-90h]
0x18000e8ae  sub     rsp, 190h
0x18000e8b5  mov     rax, cs:__security_cookie
0x18000e8bc  xor     rax, rsp
0x18000e8bf  mov     [rbp+0A0h+var_20], rax
0x18000e8c6  xorps   xmm0, xmm0
0x18000e8c9  mov     rdi, rdx
0x18000e8cc  mov     rbx, rcx
0x18000e8cf  xor     eax, eax
0x18000e8d1  xor     edx, edx; Val
0x18000e8d3  mov     [rsp+1A0h+var_128], rax
0x18000e8d8  lea     rcx, [rbp+0A0h+var_120]; void *
0x18000e8dc  mov     r8d, 100h; Size
0x18000e8e2  movups  [rsp+1A0h+var_158], xmm0
0x18000e8e7  movups  [rsp+1A0h+var_148], xmm0
0x18000e8ec  movups  [rsp+1A0h+var_138], xmm0
0x18000e8f1  call    memset_0
0x18000e8f6  mov     rcx, [rbx+10h]
0x18000e8fa  lea     rdx, [rsp+1A0h+var_138]
0x18000e8ff  mov     [rsp+1A0h+var_178], rdx
0x18000e904  lea     r9, [rsp+1A0h+var_158+4]
0x18000e909  lea     rdx, [rsp+1A0h+var_158+6]
0x18000e90e  xor     r14d, r14d
0x18000e911  mov     [rsp+1A0h+var_180], rdx
0x18000e916  lea     r8, [rsp+1A0h+var_158+2]
0x18000e91b  mov     rax, [rcx]
0x18000e91e  lea     rdx, [rsp+1A0h+var_158]
0x18000e923  mov     [rsp+1A0h+var_160], r14d
0x18000e928  mov     rax, [rax+18h]
0x18000e92c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e931  mov     esi, eax
0x18000e933  test    eax, eax
0x18000e935  jz      short loc_18000E960
0x18000e937  lea     r8, aWritesysteminf; "WriteSystemInfo.GetCpuInfo failed, 0x%0"...
0x18000e93e  mov     r10, [rbx+28h]
0x18000e942  mov     r9d, esi
0x18000e945  mov     edx, 4
0x18000e94a  mov     rcx, [r10]
0x18000e94d  mov     rax, [rcx+8]
0x18000e951  mov     rcx, r10
0x18000e954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e959  mov     eax, esi
0x18000e95b  jmp     loc_18000EA28
0x18000e960  mov     al, [rbx+82h]
0x18000e966  lea     rdx, [rbp+0A0h+var_120]
0x18000e96a  mov     rcx, [rbx+10h]
0x18000e96e  mov     r8d, 80h
0x18000e974  mov     byte ptr [rsp+1A0h+var_158+7], al
0x18000e978  mov     eax, [rbx+70h]
0x18000e97b  mov     dword ptr [rsp+1A0h+var_158+8], eax
0x18000e97f  mov     eax, [rbx+74h]
0x18000e982  mov     dword ptr [rsp+1A0h+var_158+0Ch], eax
0x18000e986  mov     eax, [rbx+7Ch]
0x18000e989  mov     dword ptr [rsp+1A0h+var_148], eax
0x18000e98d  mov     eax, [rbx+6Ch]
0x18000e990  mov     dword ptr [rsp+1A0h+var_148+4], eax
0x18000e994  movzx   eax, word ptr [rbx+84h]
0x18000e99b  mov     word ptr [rsp+1A0h+var_148+0Ch], ax
0x18000e9a0  movzx   eax, word ptr [rbx+80h]
0x18000e9a7  mov     word ptr [rsp+1A0h+var_148+0Eh], ax
0x18000e9ac  mov     rax, [rcx]
0x18000e9af  mov     rax, [rax+58h]
0x18000e9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9b8  mov     esi, eax
0x18000e9ba  test    eax, eax
0x18000e9bc  jz      short loc_18000E9CA
0x18000e9be  lea     r8, aWritesysteminf_0; "WriteSystemInfo.GetOsCsdString failed, "...
0x18000e9c5  jmp     loc_18000E93E
0x18000e9ca  lea     rcx, [rbp+0A0h+var_120]
0x18000e9ce  movzx   eax, word ptr [rcx]
0x18000e9d1  add     rcx, 2
0x18000e9d5  test    ax, ax
0x18000e9d8  jnz     short loc_18000E9CE
0x18000e9da  lea     rax, [rbp+0A0h+var_120]
0x18000e9de  sub     rcx, rax
0x18000e9e1  sar     rcx, 1
0x18000e9e4  add     ecx, ecx
0x18000e9e6  cmp     ecx, [rdi+1Ch]
0x18000e9e9  jz      short loc_18000E9F2
0x18000e9eb  mov     eax, 80070057h
0x18000e9f0  jmp     short loc_18000EA28
0x18000e9f2  lea     r9, [rsp+1A0h+var_160]; unsigned int *
0x18000e9f7  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000e9fa  lea     r8, [rbp+0A0h+var_120]; unsigned __int16 *
0x18000e9fe  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000ea01  call    ?WriteStringToPool@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAGPEAK@Z; WriteStringToPool(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,ushort *,ulong *)
0x18000ea06  test    eax, eax
0x18000ea08  jnz     short loc_18000EA28
0x18000ea0a  mov     eax, [rsp+1A0h+var_160]
0x18000ea0e  lea     r8, [rsp+1A0h+var_158]; void *
0x18000ea13  mov     edx, [rdi+14h]; unsigned int
0x18000ea16  mov     r9d, 38h ; '8'; unsigned int
0x18000ea1c  mov     rcx, rbx; struct _MINIDUMP_STATE *
0x18000ea1f  mov     dword ptr [rsp+1A0h+var_148+8], eax
0x18000ea23  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000ea28  mov     rcx, [rbp+0A0h+var_20]
0x18000ea2f  xor     rcx, rsp; StackCookie
0x18000ea32  call    __security_check_cookie
0x18000ea37  lea     r11, [rsp+1A0h+var_10]
0x18000ea3f  mov     rbx, [r11+30h]
0x18000ea43  mov     rsi, [r11+38h]
0x18000ea47  mov     rsp, r11
0x18000ea4a  pop     r14
0x18000ea4c  pop     rdi
0x18000ea4d  pop     rbp
0x18000ea4e  retn
```
