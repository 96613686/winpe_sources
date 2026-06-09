# CMsftDiscRecorder2::SendCommandGetDataFromDevice(uchar *,ulong,uchar * const,ulong,uchar *,ulong,ulong *)

- ea: `0x1800030f0`
- end: `0x180003273`
- name: `?SendCommandGetDataFromDevice@CMsftDiscRecorder2@@UEAAJPEAEKQEAEK0KPEAK@Z`
- size: `387`
- prototype: `int(CMsftDiscRecorder2 *__hidden this, unsigned __int8 *, unsigned int, unsigned __int8 *const, unsigned int, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x1800030f0`
- `0x18000327c`
- `0x1800036f0`
- `0x1800140f4`
- `0x180014134`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::SendCommandGetDataFromDevice(
        void **this,
        union _CDB *a2,
        unsigned int a3,
        struct _SENSE_DATA *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned int *a8)
{
  __int64 v10; // r9
  DWORD v13; // ebx
  const struct _GUID *v14; // r8

  v10 = *((unsigned int *)this + 58);
  if ( (v10 & 2) != 0 )
  {
    v13 = CMsftDiscRecorder2::SendCommandCommonValidation(
            (CMsftDiscRecorder2 *)this,
            a2,
            a2,
            a3,
            a4,
            a5,
            a6,
            a7,
            a8,
            1u);
    if ( (v13 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 54, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids, v13);
      }
    }
    else
    {
      v13 = CMsftDiscRecorder2::SendCommandHelper(
              (CMsftDiscRecorder2 *)(this - 1),
              this[10],
              a2,
              a3,
              a4,
              a5,
              a6,
              a7,
              a8,
              1u);
    }
    if ( (v13 & 0x80FF0000) == 0x80AA0000 )
      Imapi2Utility::SetErrorDescription(v13, (__int64)&CLSID_MsftDiscRecorder2, v14);
  }
  else
  {
    v13 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        53,
        &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
        v10,
        -2147467259);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x1800030f0  mov     rax, rsp
0x1800030f3  push    rbx
0x1800030f4  push    rbp
0x1800030f5  push    rsi
0x1800030f6  push    rdi
0x1800030f7  push    r12
0x1800030f9  push    r13
0x1800030fb  push    r14
0x1800030fd  push    r15
0x1800030ff  sub     rsp, 58h
0x180003103  mov     rsi, r9
0x180003106  mov     ebp, r8d
0x180003109  mov     r9d, [rcx+0E8h]
0x180003110  mov     r14, rdx
0x180003113  mov     rdi, rcx
0x180003116  test    r9b, 2
0x18000311a  jz      loc_1800031CB
0x180003120  mov     r15, [rsp+98h+arg_38]
0x180003128  mov     r9d, r8d; unsigned int
0x18000312b  mov     r12d, [rsp+98h+arg_30]
0x180003133  mov     r8, rdx; union _CDB *
0x180003136  mov     r13, [rsp+98h+arg_28]
0x18000313e  mov     byte ptr [rax-50h], 1
0x180003142  mov     [rax-58h], r15
0x180003146  mov     [rax-60h], r12d
0x18000314a  mov     [rax-68h], r13
0x18000314e  mov     eax, [rsp+98h+arg_20]
0x180003155  mov     [rsp+98h+var_70], eax; unsigned int
0x180003159  mov     [rsp+98h+var_78], rsi; struct _SENSE_DATA *
0x18000315e  call    ?SendCommandCommonValidation@CMsftDiscRecorder2@@AEAA?BJQEAXPEBT_CDB@@KPEAU_SENSE_DATA@@KPEAEKPEAKE@Z; CMsftDiscRecorder2::SendCommandCommonValidation(void * const,_CDB const *,ulong,_SENSE_DATA *,ulong,uchar *,ulong,ulong *,uchar)
0x180003163  mov     ebx, eax
0x180003165  test    eax, eax
0x180003167  js      loc_180003213
0x18000316d  mov     eax, [rsp+98h+arg_20]
0x180003174  lea     rcx, [rdi-8]; this
0x180003178  mov     rdx, [rcx+58h]; void *
0x18000317c  mov     r9d, ebp; unsigned int
0x18000317f  mov     [rsp+98h+var_50], 1; unsigned __int8
0x180003184  mov     r8, r14; union _CDB *
0x180003187  mov     [rsp+98h+var_58], r15; unsigned int *
0x18000318c  mov     [rsp+98h+var_60], r12d; unsigned int
0x180003191  mov     [rsp+98h+var_68], r13; unsigned __int8 *
0x180003196  mov     [rsp+98h+var_70], eax; unsigned int
0x18000319a  mov     [rsp+98h+var_78], rsi; struct _SENSE_DATA *
0x18000319f  call    ?SendCommandHelper@CMsftDiscRecorder2@@AEAA?BJQEAXPEBT_CDB@@KPEAU_SENSE_DATA@@KPEAEKPEAKE@Z; CMsftDiscRecorder2::SendCommandHelper(void * const,_CDB const *,ulong,_SENSE_DATA *,ulong,uchar *,ulong,ulong *,uchar)
0x1800031a4  mov     ebx, eax
0x1800031a6  mov     eax, ebx
0x1800031a8  and     eax, 80FF0000h
0x1800031ad  cmp     eax, 80AA0000h
0x1800031b2  jz      loc_180003260
0x1800031b8  mov     eax, ebx
0x1800031ba  add     rsp, 58h
0x1800031be  pop     r15
0x1800031c0  pop     r14
0x1800031c2  pop     r13
0x1800031c4  pop     r12
0x1800031c6  pop     rdi
0x1800031c7  pop     rsi
0x1800031c8  pop     rbp
0x1800031c9  pop     rbx
0x1800031ca  retn
0x1800031cb  mov     ebx, 80004005h
0x1800031d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031d7  lea     rax, WPP_GLOBAL_Control
0x1800031de  cmp     rcx, rax
0x1800031e1  jz      short loc_1800031B8
0x1800031e3  test    byte ptr [rcx+0BCh], 4
0x1800031ea  jz      short loc_1800031B8
0x1800031ec  cmp     byte ptr [rcx+0B9h], 3
0x1800031f3  jb      short loc_1800031B8
0x1800031f5  mov     rcx, [rcx+0B0h]
0x1800031fc  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180003203  mov     edx, 35h ; '5'
0x180003208  mov     dword ptr [rsp+98h+var_78], ebx
0x18000320c  call    WPP_SF_Dd
0x180003211  jmp     short loc_1800031B8
0x180003213  mov     rcx, cs:WPP_GLOBAL_Control
0x18000321a  lea     rax, WPP_GLOBAL_Control
0x180003221  cmp     rcx, rax
0x180003224  jz      short loc_1800031A6
0x180003226  test    byte ptr [rcx+0BCh], 4
0x18000322d  jz      loc_1800031A6
0x180003233  cmp     byte ptr [rcx+0B9h], 3
0x18000323a  jb      loc_1800031A6
0x180003240  mov     rcx, [rcx+0B0h]
0x180003247  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18000324e  mov     edx, 36h ; '6'
0x180003253  mov     r9d, ebx
0x180003256  call    WPP_SF_d
0x18000325b  jmp     loc_1800031A6
0x180003260  lea     rdx, CLSID_MsftDiscRecorder2; int
0x180003267  mov     ecx, ebx; dwMessageId
0x180003269  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18000326e  jmp     loc_1800031B8
```
