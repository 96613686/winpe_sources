# CMsftDiscRecorder2::SendCommandSendDataToDevice(uchar *,ulong,uchar * const,ulong,uchar *,ulong)

- ea: `0x180002750`
- end: `0x1800028c4`
- name: `?SendCommandSendDataToDevice@CMsftDiscRecorder2@@UEAAJPEAEKQEAEK0K@Z`
- size: `372`
- prototype: `int(CMsftDiscRecorder2 *__hidden this, unsigned __int8 *, unsigned int, unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002750`
- `0x180002fc8`
- `0x18000327c`
- `0x1800036f0`
- `0x1800140f4`
- `0x180014134`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::SendCommandSendDataToDevice(
        void **this,
        union _CDB *a2,
        unsigned int a3,
        struct _SENSE_DATA *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7)
{
  __int64 v9; // r9
  DWORD v12; // ebx
  const struct _GUID *v13; // r8

  v9 = *((unsigned int *)this + 58);
  if ( (v9 & 2) != 0 )
  {
    v12 = CMsftDiscRecorder2::SendCommandCommonValidation((CMsftDiscRecorder2 *)this, a2, a2, a3, a4, a5, a6, a7, 0, 0);
    if ( (v12 & 0x80000000) == 0 )
    {
      v12 = CMsftDiscRecorder2::SendCommandHelper(
              (CMsftDiscRecorder2 *)(this - 1),
              this[10],
              a2,
              a3,
              a4,
              a5,
              a6,
              a7,
              0,
              0);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 52, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, v12);
    }
    if ( (v12 & 0x80FF0000) == 0x80AA0000 )
      Imapi2Utility::SetErrorDescription(v12, (__int64)&CLSID_MsftDiscRecorder2, v13);
  }
  else
  {
    v12 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        51,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        v9,
        -2147467259);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180002750  push    rbx
0x180002752  push    rbp
0x180002753  push    rsi
0x180002754  push    rdi
0x180002755  push    r12
0x180002757  push    r13
0x180002759  push    r14
0x18000275b  push    r15
0x18000275d  sub     rsp, 58h
0x180002761  mov     rsi, r9
0x180002764  mov     ebp, r8d
0x180002767  mov     r9d, [rcx+0E8h]
0x18000276e  mov     r14, rdx
0x180002771  mov     rdi, rcx
0x180002774  test    r9b, 2
0x180002778  jnz     short loc_1800027D1
0x18000277a  mov     ebx, 80004005h
0x18000277f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002786  lea     rax, WPP_GLOBAL_Control
0x18000278d  cmp     rcx, rax
0x180002790  jz      loc_1800028B1
0x180002796  test    byte ptr [rcx+0BCh], 4
0x18000279d  jz      loc_1800028B1
0x1800027a3  cmp     byte ptr [rcx+0B9h], 3
0x1800027aa  jb      loc_1800028B1
0x1800027b0  mov     rcx, [rcx+0B0h]
0x1800027b7  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x1800027be  mov     edx, 33h ; '3'
0x1800027c3  mov     dword ptr [rsp+98h+var_78], ebx
0x1800027c7  call    WPP_SF_Dd
0x1800027cc  jmp     loc_1800028B1
0x1800027d1  mov     r15d, [rsp+98h+arg_30]
0x1800027d9  mov     r9d, ebp; unsigned int
0x1800027dc  mov     r12, [rsp+98h+arg_28]
0x1800027e4  mov     r8, r14; union _CDB *
0x1800027e7  mov     r13d, [rsp+98h+arg_20]
0x1800027ef  mov     [rsp+98h+var_50], 0; unsigned __int8
0x1800027f4  mov     [rsp+98h+var_58], 0; unsigned int *
0x1800027fd  mov     [rsp+98h+var_60], r15d; unsigned int
0x180002802  mov     [rsp+98h+var_68], r12; unsigned __int8 *
0x180002807  mov     [rsp+98h+var_70], r13d; unsigned int
0x18000280c  mov     [rsp+98h+var_78], rsi; struct _SENSE_DATA *
0x180002811  call    ?SendCommandCommonValidation@CMsftDiscRecorder2@@AEAA?BJQEAXPEBT_CDB@@KPEAU_SENSE_DATA@@KPEAEKPEAKE@Z; CMsftDiscRecorder2::SendCommandCommonValidation(void * const,_CDB const *,ulong,_SENSE_DATA *,ulong,uchar *,ulong,ulong *,uchar)
0x180002816  mov     ebx, eax
0x180002818  test    eax, eax
0x18000281a  jns     short loc_18000285E
0x18000281c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002823  lea     rax, WPP_GLOBAL_Control
0x18000282a  cmp     rcx, rax
0x18000282d  jz      short loc_180002895
0x18000282f  test    byte ptr [rcx+0BCh], 4
0x180002836  jz      short loc_180002895
0x180002838  cmp     byte ptr [rcx+0B9h], 3
0x18000283f  jb      short loc_180002895
0x180002841  mov     rcx, [rcx+0B0h]
0x180002848  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18000284f  mov     edx, 34h ; '4'
0x180002854  mov     r9d, ebx
0x180002857  call    WPP_SF_d
0x18000285c  jmp     short loc_180002895
0x18000285e  mov     [rsp+98h+var_50], 0; unsigned __int8
0x180002863  lea     rcx, [rdi-8]; this
0x180002867  mov     rdx, [rcx+58h]; void *
0x18000286b  mov     r9d, ebp; unsigned int
0x18000286e  mov     [rsp+98h+var_58], 0; unsigned int *
0x180002877  mov     r8, r14; union _CDB *
0x18000287a  mov     [rsp+98h+var_60], r15d; unsigned int
0x18000287f  mov     [rsp+98h+var_68], r12; unsigned __int8 *
0x180002884  mov     [rsp+98h+var_70], r13d; unsigned int
0x180002889  mov     [rsp+98h+var_78], rsi; struct _SENSE_DATA *
0x18000288e  call    ?SendCommandHelper@CMsftDiscRecorder2@@AEAA?BJQEAXPEBT_CDB@@KPEAU_SENSE_DATA@@KPEAEKPEAKE@Z; CMsftDiscRecorder2::SendCommandHelper(void * const,_CDB const *,ulong,_SENSE_DATA *,ulong,uchar *,ulong,ulong *,uchar)
0x180002893  mov     ebx, eax
0x180002895  mov     eax, ebx
0x180002897  and     eax, 80FF0000h
0x18000289c  cmp     eax, 80AA0000h
0x1800028a1  jnz     short loc_1800028B1
0x1800028a3  lea     rdx, CLSID_MsftDiscRecorder2; int
0x1800028aa  mov     ecx, ebx; dwMessageId
0x1800028ac  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x1800028b1  mov     eax, ebx
0x1800028b3  add     rsp, 58h
0x1800028b7  pop     r15
0x1800028b9  pop     r14
0x1800028bb  pop     r13
0x1800028bd  pop     r12
0x1800028bf  pop     rdi
0x1800028c0  pop     rsi
0x1800028c1  pop     rbp
0x1800028c2  pop     rbx
0x1800028c3  retn
```
