# FltpLogEventWithObjectID

- ea: `0x180067030`
- end: `0x18006726c`
- name: `FltpLogEventWithObjectID`
- size: `572`
- prototype: `__int64 __usercall@<rax>(PCEVENT_DESCRIPTOR EventDescriptor@<rcx>, __int64)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x18004c810`
- `0x18004d410`
- `0x180055e20`
- `0x180068790`
- `0x180068900`
- `0x180069c90`
- `0x180070c80`
- `0x180078690`

## callees

- `0x180009f20`
- `0x1800247a0`
- `0x18004db20`
- `0x180067030`

## import_xrefs

- `ntoskrnl!RtlSystemTimeToLocalTime` at `0x180067162`
- `ntoskrnl!RtlSystemTimeToLocalTime` at `0x180067162`
- `ntoskrnl!EtwWrite` at `0x180067245`
- `ntoskrnl!EtwWrite` at `0x180067245`
- `ntoskrnl!RtlSecondsSince1970ToTime` at `0x18006714c`
- `ntoskrnl!RtlSecondsSince1970ToTime` at `0x18006714c`

## pseudocode

```c
void __fastcall FltpLogEventWithObjectID(
        PCEVENT_DESCRIPTOR EventDescriptor,
        int a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int64 a5)
{
  ULONG v8; // r9d
  unsigned int DriverVersion; // eax
  __int64 v10; // rdx
  __int64 v11; // rax
  unsigned int v12; // edx
  __int64 v13; // rax
  ULONG v14; // r9d
  struct _EVENT_DATA_DESCRIPTOR *v15; // rcx
  unsigned __int64 v16; // rcx
  __int64 v17; // rax
  ULONG v18; // r9d
  __int64 v19; // rax
  __int64 v20; // rax
  _WORD v21[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v22; // [rsp+34h] [rbp-CCh] BYREF
  int v23; // [rsp+38h] [rbp-C8h] BYREF
  int v24; // [rsp+3Ch] [rbp-C4h] BYREF
  ULONG ElapsedSeconds; // [rsp+40h] [rbp-C0h] BYREF
  LARGE_INTEGER Time; // [rsp+48h] [rbp-B8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  int *v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  int *v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+78h] [rbp-88h]
  __int16 *v32; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+90h] [rbp-70h]
  int v35; // [rsp+98h] [rbp-68h]
  int v36; // [rsp+9Ch] [rbp-64h]
  LARGE_INTEGER *p_Time; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  int v39; // [rsp+148h] [rbp+48h] BYREF

  v39 = a2;
  v23 = 0;
  v24 = 0;
  ElapsedSeconds = 0;
  Time.QuadPart = 0;
  v22 = 0;
  v21[0] = 0;
  if ( qword_18003E758 )
  {
    *(_QWORD *)&UserData.Size = 4;
    UserData.Ptr = (unsigned __int64)&v39;
    v8 = 1;
    if ( a3 )
    {
      DriverVersion = FltpGetDriverVersion(a3, (unsigned int)&v23, (unsigned int)&v24, (unsigned int)&ElapsedSeconds, 0);
      if ( (int)FltpDbgStatus(DriverVersion, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 12243, 0) < 0 )
        return;
      v10 = *(_QWORD *)(a3 + 48);
      v28 = &v23;
      v30 = &v24;
      v29 = 4;
      v31 = 4;
      v22 = *(_WORD *)(v10 + 24) >> 1;
      v32 = &v22;
      v33 = 2;
      v11 = *(_QWORD *)(v10 + 32);
      v35 = *(unsigned __int16 *)(v10 + 24);
      v34 = v11;
      v36 = 0;
      RtlSecondsSince1970ToTime(ElapsedSeconds, &Time);
      RtlSystemTimeToLocalTime(&Time, &Time);
      v38 = 8;
      p_Time = &Time;
      v8 = 6;
    }
    if ( a4 )
    {
      v12 = *a4;
      v21[0] = *a4 >> 1;
      v13 = v8;
      v14 = v8 + 1;
      v13 *= 2;
      *(&UserData.Ptr + v13) = (unsigned __int64)v21;
      *((_QWORD *)&UserData.Size + v13) = 2;
      v15 = &UserData + v14;
      v8 = v14 + 1;
      v15->Ptr = *((_QWORD *)a4 + 1);
      *(_QWORD *)&v15->Size = v12;
    }
    v16 = a5;
    if ( a5 )
    {
      if ( !a4 )
      {
        v17 = 2LL * v8;
        v21[0] = 0;
        v18 = v8 + 1;
        *(&UserData.Ptr + v17) = (unsigned __int64)v21;
        *((_QWORD *)&UserData.Size + v17) = 2;
        v19 = 2LL * v18;
        v8 = v18 + 1;
        *(&UserData.Ptr + v19) = 0;
        *((_QWORD *)&UserData.Size + v19) = 0;
      }
      v20 = 2LL * v8++;
      *(&UserData.Ptr + v20) = v16;
      *((_QWORD *)&UserData.Size + v20) = 16;
    }
    EtwWrite(qword_18003E758, EventDescriptor, 0, v8, &UserData);
  }
}

```

## disassembly

```asm
0x180067030  mov     [rsp-8+arg_8], edx
0x180067034  push    rbp
0x180067035  push    rbx
0x180067036  push    rsi
0x180067037  push    rdi
0x180067038  push    r14
0x18006703a  lea     rbp, [rsp-10h]
0x18006703f  sub     rsp, 110h
0x180067046  mov     rax, cs:__security_cookie
0x18006704d  xor     rax, rsp
0x180067050  mov     [rbp+30h+var_30], rax
0x180067054  xor     r14d, r14d
0x180067057  mov     rbx, r9
0x18006705a  cmp     cs:qword_18003E758, r14
0x180067061  mov     rdi, r8
0x180067064  mov     rsi, rcx
0x180067067  mov     [rsp+130h+var_F8], r14d
0x18006706c  mov     [rsp+130h+var_F4], r14d
0x180067071  mov     [rsp+130h+ElapsedSeconds], r14d
0x180067076  mov     qword ptr [rsp+130h+Time], r14
0x18006707b  mov     [rsp+130h+var_FC], r14w
0x180067081  mov     [rsp+130h+var_100], r14w
0x180067087  jz      loc_180067251
0x18006708d  mov     qword ptr [rsp+130h+var_E0.Size], 4
0x180067096  lea     rax, [rbp+30h+arg_8]
0x18006709a  mov     [rsp+130h+var_E0.Ptr], rax
0x18006709f  mov     r9d, 1
0x1800670a5  test    r8, r8
0x1800670a8  jz      loc_180067185
0x1800670ae  lea     r9, [rsp+130h+ElapsedSeconds]
0x1800670b3  mov     [rsp+130h+UserData], r14
0x1800670b8  lea     r8, [rsp+130h+var_F4]
0x1800670bd  mov     rcx, rdi
0x1800670c0  lea     rdx, [rsp+130h+var_F8]
0x1800670c5  call    FltpGetDriverVersion
0x1800670ca  mov     r8d, 2FD3h
0x1800670d0  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x1800670d7  xor     r9d, r9d
0x1800670da  mov     ecx, eax
0x1800670dc  call    FltpDbgStatus
0x1800670e1  test    eax, eax
0x1800670e3  js      loc_180067251
0x1800670e9  mov     rdx, [rdi+30h]
0x1800670ed  lea     rax, [rsp+130h+var_F8]
0x1800670f2  mov     [rsp+130h+var_D0], rax
0x1800670f7  lea     rax, [rsp+130h+var_F4]
0x1800670fc  mov     [rsp+130h+var_C0], rax
0x180067101  mov     [rsp+130h+var_C8], 4
0x18006710a  mov     [rsp+130h+var_B8], 4
0x180067113  movzx   eax, word ptr [rdx+18h]
0x180067117  shr     ax, 1
0x18006711a  mov     [rsp+130h+var_FC], ax
0x18006711f  lea     rax, [rsp+130h+var_FC]
0x180067124  mov     [rbp+30h+var_B0], rax
0x180067128  mov     [rbp+30h+var_A8], 2
0x180067130  movzx   ecx, word ptr [rdx+18h]
0x180067134  mov     rax, [rdx+20h]
0x180067138  lea     rdx, [rsp+130h+Time]; Time
0x18006713d  mov     [rbp+30h+var_98], ecx
0x180067140  mov     ecx, [rsp+130h+ElapsedSeconds]; ElapsedSeconds
0x180067144  mov     [rbp+30h+var_A0], rax
0x180067148  mov     [rbp+30h+var_94], r14d
0x18006714c  call    cs:__imp_RtlSecondsSince1970ToTime
0x180067153  nop     dword ptr [rax+rax+00h]
0x180067158  lea     rdx, [rsp+130h+Time]; LocalTime
0x18006715d  lea     rcx, [rsp+130h+Time]; SystemTime
0x180067162  call    cs:__imp_RtlSystemTimeToLocalTime
0x180067169  nop     dword ptr [rax+rax+00h]
0x18006716e  lea     rax, [rsp+130h+Time]
0x180067173  mov     [rbp+30h+var_88], 8
0x18006717b  mov     [rbp+30h+var_90], rax
0x18006717f  mov     r9d, 6
0x180067185  test    rbx, rbx
0x180067188  jz      short loc_1800671D4
0x18006718a  movzx   edx, word ptr [rbx]
0x18006718d  lea     rcx, [rsp+130h+var_100]
0x180067192  movzx   eax, dx
0x180067195  shr     ax, 1
0x180067198  mov     [rsp+130h+var_100], ax
0x18006719d  mov     eax, r9d
0x1800671a0  inc     r9d
0x1800671a3  add     rax, rax
0x1800671a6  mov     [rsp+rax*8+130h+var_E0.Ptr], rcx
0x1800671ab  lea     rcx, [rsp+130h+var_E0]
0x1800671b0  mov     qword ptr [rsp+rax*8+130h+var_E0.Size], 2
0x1800671b9  mov     eax, r9d
0x1800671bc  shl     rax, 4
0x1800671c0  add     rcx, rax
0x1800671c3  mov     rax, [rbx+8]
0x1800671c7  inc     r9d
0x1800671ca  mov     [rcx], rax
0x1800671cd  mov     [rcx+8], edx
0x1800671d0  mov     [rcx+0Ch], r14d
0x1800671d4  mov     rcx, [rbp+30h+arg_20]
0x1800671d8  test    rcx, rcx
0x1800671db  jz      short loc_18006722E
0x1800671dd  test    rbx, rbx
0x1800671e0  jnz     short loc_180067217
0x1800671e2  mov     eax, r9d
0x1800671e5  lea     rdx, [rsp+130h+var_100]
0x1800671ea  add     rax, rax
0x1800671ed  mov     [rsp+130h+var_100], r14w
0x1800671f3  inc     r9d
0x1800671f6  mov     [rsp+rax*8+130h+var_E0.Ptr], rdx
0x1800671fb  mov     qword ptr [rsp+rax*8+130h+var_E0.Size], 2
0x180067204  mov     eax, r9d
0x180067207  add     rax, rax
0x18006720a  inc     r9d
0x18006720d  mov     [rsp+rax*8+130h+var_E0.Ptr], r14
0x180067212  mov     qword ptr [rsp+rax*8+130h+var_E0.Size], r14
0x180067217  mov     eax, r9d
0x18006721a  add     rax, rax
0x18006721d  inc     r9d; UserDataCount
0x180067220  mov     [rsp+rax*8+130h+var_E0.Ptr], rcx
0x180067225  mov     qword ptr [rsp+rax*8+130h+var_E0.Size], 10h
0x18006722e  mov     rcx, cs:qword_18003E758; RegHandle
0x180067235  lea     rax, [rsp+130h+var_E0]
0x18006723a  xor     r8d, r8d; ActivityId
0x18006723d  mov     [rsp+130h+UserData], rax; UserData
0x180067242  mov     rdx, rsi; EventDescriptor
0x180067245  call    cs:__imp_EtwWrite
0x18006724c  nop     dword ptr [rax+rax+00h]
0x180067251  mov     rcx, [rbp+30h+var_30]
0x180067255  xor     rcx, rsp; StackCookie
0x180067258  call    __security_check_cookie
0x18006725d  add     rsp, 110h
0x180067264  pop     r14
0x180067266  pop     rdi
0x180067267  pop     rsi
0x180067268  pop     rbx
0x180067269  pop     rbp
0x18006726a  retn
```
