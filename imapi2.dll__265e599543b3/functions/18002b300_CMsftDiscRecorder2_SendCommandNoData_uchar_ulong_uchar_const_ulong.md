# CMsftDiscRecorder2::SendCommandNoData(uchar *,ulong,uchar * const,ulong)

- ea: `0x18002b300`
- end: `0x18002b46a`
- name: `?SendCommandNoData@CMsftDiscRecorder2@@UEAAJPEAEKQEAEK@Z`
- size: `362`
- prototype: `int(CMsftDiscRecorder2 *__hidden this, unsigned __int8 *, unsigned int, unsigned __int8 *const, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x18000327c`
- `0x1800036f0`
- `0x1800140f4`
- `0x180014134`
- `0x18002b300`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::SendCommandNoData(
        void **this,
        union _CDB *a2,
        unsigned int a3,
        struct _SENSE_DATA *a4,
        unsigned int a5)
{
  __int64 v7; // r9
  DWORD v10; // ebx
  const struct _GUID *v11; // r8

  v7 = *((unsigned int *)this + 58);
  if ( (v7 & 2) != 0 )
  {
    v10 = CMsftDiscRecorder2::SendCommandCommonValidation((CMsftDiscRecorder2 *)this, a2, a2, a3, a4, a5, 0, 0, 0, 0);
    if ( (v10 & 0x80000000) == 0 )
    {
      v10 = CMsftDiscRecorder2::SendCommandHelper(
              (CMsftDiscRecorder2 *)(this - 1),
              this[10],
              a2,
              a3,
              a4,
              a5,
              0,
              0,
              0,
              0);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 50, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, v10);
    }
    if ( (v10 & 0x80FF0000) == 0x80AA0000 )
      Imapi2Utility::SetErrorDescription(v10, (__int64)&CLSID_MsftDiscRecorder2, v11);
  }
  else
  {
    v10 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        49,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        v7,
        -2147467259);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18002b300  push    rbx
0x18002b302  push    rbp
0x18002b303  push    rsi
0x18002b304  push    rdi
0x18002b305  push    r14
0x18002b307  push    r15
0x18002b309  sub     rsp, 58h
0x18002b30d  mov     rdi, r9
0x18002b310  mov     esi, r8d
0x18002b313  mov     r9d, [rcx+0E8h]
0x18002b31a  mov     rbp, rdx
0x18002b31d  mov     r15, rcx
0x18002b320  test    r9b, 2
0x18002b324  jnz     short loc_18002B37D
0x18002b326  mov     ebx, 80004005h
0x18002b32b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b332  lea     rax, WPP_GLOBAL_Control
0x18002b339  cmp     rcx, rax
0x18002b33c  jz      loc_18002B45B
0x18002b342  test    byte ptr [rcx+0BCh], 4
0x18002b349  jz      loc_18002B45B
0x18002b34f  cmp     byte ptr [rcx+0B9h], 3
0x18002b356  jb      loc_18002B45B
0x18002b35c  mov     rcx, [rcx+0B0h]
0x18002b363  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002b36a  mov     edx, 31h ; '1'
0x18002b36f  mov     dword ptr [rsp+88h+var_68], ebx
0x18002b373  call    WPP_SF_Dd
0x18002b378  jmp     loc_18002B45B
0x18002b37d  mov     r14d, [rsp+88h+arg_20]
0x18002b385  mov     r9d, esi; unsigned int
0x18002b388  mov     [rsp+88h+var_40], 0; unsigned __int8
0x18002b38d  mov     r8, rbp; union _CDB *
0x18002b390  mov     [rsp+88h+var_48], 0; unsigned int *
0x18002b399  mov     [rsp+88h+var_50], 0; unsigned int
0x18002b3a1  mov     [rsp+88h+var_58], 0; unsigned __int8 *
0x18002b3aa  mov     [rsp+88h+var_60], r14d; unsigned int
0x18002b3af  mov     [rsp+88h+var_68], rdi; struct _SENSE_DATA *
0x18002b3b4  call    ?SendCommandCommonValidation@CMsftDiscRecorder2@@AEAA?BJQEAXPEBT_CDB@@KPEAU_SENSE_DATA@@KPEAEKPEAKE@Z; CMsftDiscRecorder2::SendCommandCommonValidation(void * const,_CDB const *,ulong,_SENSE_DATA *,ulong,uchar *,ulong,ulong *,uchar)
0x18002b3b9  mov     ebx, eax
0x18002b3bb  test    eax, eax
0x18002b3bd  jns     short loc_18002B401
0x18002b3bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3c6  lea     rax, WPP_GLOBAL_Control
0x18002b3cd  cmp     rcx, rax
0x18002b3d0  jz      short loc_18002B43F
0x18002b3d2  test    byte ptr [rcx+0BCh], 4
0x18002b3d9  jz      short loc_18002B43F
0x18002b3db  cmp     byte ptr [rcx+0B9h], 3
0x18002b3e2  jb      short loc_18002B43F
0x18002b3e4  mov     rcx, [rcx+0B0h]
0x18002b3eb  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002b3f2  mov     edx, 32h ; '2'
0x18002b3f7  mov     r9d, ebx
0x18002b3fa  call    WPP_SF_d
0x18002b3ff  jmp     short loc_18002B43F
0x18002b401  mov     [rsp+88h+var_40], 0; unsigned __int8
0x18002b406  lea     rcx, [r15-8]; this
0x18002b40a  mov     rdx, [rcx+58h]; void *
0x18002b40e  mov     r9d, esi; unsigned int
0x18002b411  mov     [rsp+88h+var_48], 0; unsigned int *
0x18002b41a  mov     r8, rbp; union _CDB *
0x18002b41d  mov     [rsp+88h+var_50], 0; unsigned int
0x18002b425  mov     [rsp+88h+var_58], 0; unsigned __int8 *
0x18002b42e  mov     [rsp+88h+var_60], r14d; unsigned int
0x18002b433  mov     [rsp+88h+var_68], rdi; struct _SENSE_DATA *
0x18002b438  call    ?SendCommandHelper@CMsftDiscRecorder2@@AEAA?BJQEAXPEBT_CDB@@KPEAU_SENSE_DATA@@KPEAEKPEAKE@Z; CMsftDiscRecorder2::SendCommandHelper(void * const,_CDB const *,ulong,_SENSE_DATA *,ulong,uchar *,ulong,ulong *,uchar)
0x18002b43d  mov     ebx, eax
0x18002b43f  mov     eax, ebx
0x18002b441  and     eax, 80FF0000h
0x18002b446  cmp     eax, 80AA0000h
0x18002b44b  jnz     short loc_18002B45B
0x18002b44d  lea     rdx, CLSID_MsftDiscRecorder2; int
0x18002b454  mov     ecx, ebx; dwMessageId
0x18002b456  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18002b45b  mov     eax, ebx
0x18002b45d  add     rsp, 58h
0x18002b461  pop     r15
0x18002b463  pop     r14
0x18002b465  pop     rdi
0x18002b466  pop     rsi
0x18002b467  pop     rbp
0x18002b468  pop     rbx
0x18002b469  retn
```
