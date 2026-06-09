# FTShutdownCallback

- ea: `0x140002a00`
- end: `0x140002d61`
- name: `FTShutdownCallback`
- size: `865`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002a00`
- `0x140002d68`
- `0x140003510`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140002b24`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140002b24`
- `ntoskrnl!IoWMIWriteEvent` at `0x140002cd0`
- `ntoskrnl!IoWMIWriteEvent` at `0x140002cd0`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140002ba9`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140002ba9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002d2b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004039`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002d2b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140004039`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002d11`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004020`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002d11`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004020`
- `FLTMGR!FltGetRequestorProcessId` at `0x140002b7f`
- `FLTMGR!FltGetRequestorProcessId` at `0x140002b7f`
- `FLTMGR!FltReleaseContext` at `0x140002ced`
- `FLTMGR!FltReleaseContext` at `0x140003ffd`
- `FLTMGR!FltReleaseContext` at `0x140002ced`
- `FLTMGR!FltReleaseContext` at `0x140003ffd`
- `FLTMGR!FltGetRequestorProcess` at `0x140002b95`
- `FLTMGR!FltGetRequestorProcess` at `0x140002b95`
- `FLTMGR!FltGetVolumeContext` at `0x140002bd7`
- `FLTMGR!FltGetVolumeContext` at `0x140002bd7`

## pseudocode

```c
__int64 __fastcall FTShutdownCallback(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  unsigned int MajorFunction; // edi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  struct _KPROCESS *RequestorProcess; // rax
  int i; // ebx
  int v8; // edx
  int v9; // r8d
  char *v10; // rcx
  int v11; // r8d
  int v13; // [rsp+30h] [rbp-2B8h] BYREF
  PVOID P; // [rsp+38h] [rbp-2B0h] BYREF
  int v15[4]; // [rsp+40h] [rbp-2A8h] BYREF
  int v16[2]; // [rsp+50h] [rbp-298h] BYREF
  __int64 v17; // [rsp+58h] [rbp-290h]
  __int16 v18; // [rsp+60h] [rbp-288h]
  bool v19; // [rsp+62h] [rbp-286h]
  int v20; // [rsp+63h] [rbp-285h]
  char v21; // [rsp+67h] [rbp-281h]
  __int64 v22; // [rsp+68h] [rbp-280h]
  PFLT_CONTEXT Context[2]; // [rsp+70h] [rbp-278h] BYREF
  __int64 v24; // [rsp+80h] [rbp-268h]
  LONGLONG v25; // [rsp+88h] [rbp-260h]
  char v26; // [rsp+90h] [rbp-258h]
  int v27; // [rsp+91h] [rbp-257h]
  __int16 v28; // [rsp+95h] [rbp-253h]
  char v29; // [rsp+97h] [rbp-251h]
  __int64 v30; // [rsp+98h] [rbp-250h]
  int v31; // [rsp+A0h] [rbp-248h]
  int v32; // [rsp+A4h] [rbp-244h]
  __int64 v33; // [rsp+A8h] [rbp-240h]
  __int64 v34; // [rsp+B0h] [rbp-238h]
  __int64 v35; // [rsp+B8h] [rbp-230h]
  __int64 v36; // [rsp+C0h] [rbp-228h]
  __int64 v37; // [rsp+C8h] [rbp-220h]
  __int64 v38; // [rsp+D0h] [rbp-218h]
  __int64 v39; // [rsp+D8h] [rbp-210h]
  __int64 v40; // [rsp+E0h] [rbp-208h]
  __int64 v41; // [rsp+E8h] [rbp-200h]
  __int64 v42; // [rsp+F0h] [rbp-1F8h]
  int WnodeEventItem; // [rsp+100h] [rbp-1E8h] BYREF
  __int128 v44; // [rsp+104h] [rbp-1E4h]
  _BYTE v45[44]; // [rsp+114h] [rbp-1D4h] BYREF
  _BYTE v46[384]; // [rsp+140h] [rbp-1A8h] BYREF

  P = 0;
  v15[0] = 0;
  v13 = 0;
  WnodeEventItem = 0;
  v44 = 0;
  memset(v45, 0, sizeof(v45));
  *(_QWORD *)v16 = 0;
  v17 = 0;
  v18 = 2;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  *(_OWORD *)Context = 0;
  v24 = 0;
  v25 = 0;
  v26 = 2;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = -1;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  MajorFunction = CallbackData->Iopb->MajorFunction;
  if ( !IoGetTopLevelIrp() )
  {
    P = v46;
    v16[0] = CallbackData->IoStatus.Status;
    Iopb = CallbackData->Iopb;
    LOWORD(v16[1]) = *(_WORD *)&Iopb->MajorFunction;
    Context[1] = *(PFLT_CONTEXT *)(a2 + 32);
    HIBYTE(v18) = (Iopb->IrpFlags & 2) != 0;
    v19 = (CallbackData->Flags & 2) != 0;
    LODWORD(v24) = FltGetRequestorProcessId(CallbackData);
    RequestorProcess = FltGetRequestorProcess(CallbackData);
    v25 = RequestorProcess ? PsGetProcessCreateTimeQuadPart(RequestorProcess) : 0LL;
    if ( FltGetVolumeContext((PFLT_FILTER)WmiRegistrationContext.SecurityDescriptor, *(PFLT_VOLUME *)(a2 + 16), Context) >= 0 )
    {
      LOWORD(WnodeEventItem) = 64;
      *(_DWORD *)&v45[24] = 1179648;
      LOWORD(v44) = CallbackData->Iopb->MajorFunction;
      *(_OWORD *)&v45[4] = FT_MessageGuid;
      *(_QWORD *)&v45[28] = v46;
      *(_DWORD *)&v45[36] = 0;
      for ( i = 0; ; ++i )
      {
        v15[1] = i;
        if ( i >= 8 )
          break;
        v8 = *((_DWORD *)LogSessions + 10 * i + 3);
        v9 = *((_DWORD *)LogSessions + 10 * i + 5);
        v10 = (char *)LogSessions + 40 * i;
        *(_QWORD *)((char *)&v44 + 4) = *(_QWORD *)v10;
        if ( v8 )
        {
          if ( v8 == *((_DWORD *)v10 + 3) )
          {
            if ( _bittest(&v9, MajorFunction) )
            {
              v11 = *((_DWORD *)v10 + 8);
              if ( (v11 & 0x4000000) != 0 || (v11 & *((_DWORD *)Context[0] + 120)) != 0 )
              {
                if ( !(unsigned __int8)FormatFileTraceEvent((int)v10, (int)v16, (int)&v13, (int)v15, (size_t)&P) )
                  break;
                IoWMIWriteEvent(&WnodeEventItem);
              }
            }
          }
        }
      }
    }
  }
  if ( Context[0] )
    FltReleaseContext(Context[0]);
  if ( v13 == 1 )
  {
    ExFreeToNPagedLookasideList(&Lookaside, P);
  }
  else if ( v13 == 2 )
  {
    ExFreePoolWithTag(P, 0x72744C46u);
  }
  return 1;
}

```

## disassembly

```asm
0x140002a00  mov     r11, rsp
0x140002a03  mov     [r11+18h], rbx
0x140002a07  push    rsi
0x140002a08  push    rdi
0x140002a09  push    r14
0x140002a0b  sub     rsp, 2D0h
0x140002a12  mov     rax, cs:WmiRegistrationContext.DeviceExtension
0x140002a19  xor     rax, rsp
0x140002a1c  mov     [rsp+2E8h+var_28], rax
0x140002a24  mov     rsi, rdx
0x140002a27  mov     rbx, rcx
0x140002a2a  xor     r14d, r14d
0x140002a2d  mov     [rsp+2E8h+P], r14
0x140002a32  mov     [rsp+2E8h+var_2A8], r14d
0x140002a37  mov     [rsp+2E8h+var_2B8], r14d
0x140002a3c  mov     [r11-1E8h], r14d
0x140002a43  xorps   xmm0, xmm0
0x140002a46  xor     eax, eax
0x140002a48  movups  [rsp+2E8h+var_1E4], xmm0
0x140002a50  movups  [rsp+2E8h+var_1D4], xmm0
0x140002a58  movups  [rsp+2E8h+var_1C4], xmm0
0x140002a60  movups  [rsp+2E8h+var_1C4+0Ch], xmm0
0x140002a68  mov     qword ptr [rsp+2E8h+var_298], r14
0x140002a6d  mov     [rsp+2E8h+var_290], r14
0x140002a72  mov     [rsp+2E8h+var_288], 2
0x140002a79  mov     [rsp+2E8h+var_286], r14b
0x140002a7e  mov     [rsp+2E8h+var_285], eax
0x140002a82  mov     [rsp+2E8h+var_281], al
0x140002a86  mov     [rsp+2E8h+var_280], r14
0x140002a8b  movdqa  xmmword ptr [rsp+2E8h+Context], xmm0
0x140002a91  mov     [r11-268h], r14
0x140002a98  mov     [r11-260h], r14
0x140002a9f  mov     [rsp+2E8h+var_258], 2
0x140002aa7  mov     [rsp+2E8h+var_257], eax
0x140002aae  mov     [rsp+2E8h+var_253], ax
0x140002ab6  mov     [rsp+2E8h+var_251], al
0x140002abd  mov     [r11-250h], r14
0x140002ac4  mov     [rsp+2E8h+var_248], 0FFFFFFFFh
0x140002acf  mov     [rsp+2E8h+var_244], eax
0x140002ad6  mov     [r11-240h], r14
0x140002add  mov     [r11-238h], r14
0x140002ae4  mov     [r11-230h], r14
0x140002aeb  mov     [r11-228h], r14
0x140002af2  mov     [r11-220h], r14
0x140002af9  mov     [r11-218h], r14
0x140002b00  mov     [r11-210h], r14
0x140002b07  mov     [r11-208h], r14
0x140002b0e  mov     [r11-200h], r14
0x140002b15  mov     [r11-1F8h], r14
0x140002b1c  mov     rax, [rcx+10h]
0x140002b20  movzx   edi, byte ptr [rax+4]
0x140002b24  call    cs:__imp_IoGetTopLevelIrp
0x140002b2b  nop     dword ptr [rax+rax+00h]
0x140002b30  test    rax, rax
0x140002b33  jnz     loc_140002CE3
0x140002b39  lea     rax, [rsp+2E8h+var_1A8]
0x140002b41  mov     [rsp+2E8h+P], rax
0x140002b46  mov     eax, [rbx+18h]
0x140002b49  mov     [rsp+2E8h+var_298], eax
0x140002b4d  mov     rcx, [rbx+10h]
0x140002b51  mov     al, [rcx+4]
0x140002b54  mov     byte ptr [rsp+2E8h+var_298+4], al
0x140002b58  mov     al, [rcx+5]
0x140002b5b  mov     byte ptr [rsp+2E8h+var_298+5], al
0x140002b5f  mov     rax, [rsi+20h]
0x140002b63  mov     [rsp+2E8h+Context+8], rax
0x140002b68  mov     eax, [rcx]
0x140002b6a  shr     eax, 1
0x140002b6c  and     al, 1
0x140002b6e  mov     byte ptr [rsp+2E8h+var_288+1], al
0x140002b72  mov     eax, [rbx]
0x140002b74  shr     eax, 1
0x140002b76  and     al, 1
0x140002b78  mov     [rsp+2E8h+var_286], al
0x140002b7c  mov     rcx, rbx; CallbackData
0x140002b7f  call    cs:__imp_FltGetRequestorProcessId
0x140002b86  nop     dword ptr [rax+rax+00h]
0x140002b8b  mov     dword ptr [rsp+2E8h+var_268], eax
0x140002b92  mov     rcx, rbx; CallbackData
0x140002b95  call    cs:__imp_FltGetRequestorProcess
0x140002b9c  nop     dword ptr [rax+rax+00h]
0x140002ba1  test    rax, rax
0x140002ba4  jz      short loc_140002BBF
0x140002ba6  mov     rcx, rax; Process
0x140002ba9  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x140002bb0  nop     dword ptr [rax+rax+00h]
0x140002bb5  mov     [rsp+2E8h+var_260], rax
0x140002bbd  jmp     short loc_140002BC7
0x140002bbf  mov     [rsp+2E8h+var_260], r14
0x140002bc7  lea     r8, [rsp+2E8h+Context]; Context
0x140002bcc  mov     rdx, [rsi+10h]; Volume
0x140002bd0  mov     rcx, cs:WmiRegistrationContext.SecurityDescriptor; Filter
0x140002bd7  call    cs:__imp_FltGetVolumeContext
0x140002bde  nop     dword ptr [rax+rax+00h]
0x140002be3  test    eax, eax
0x140002be5  js      loc_140002CE3
0x140002beb  mov     eax, 40h ; '@'
0x140002bf0  mov     word ptr [rsp+2E8h+WnodeEventItem], ax
0x140002bf8  mov     dword ptr [rsp+2E8h+var_1C4+8], 120000h
0x140002c03  mov     rax, [rbx+10h]
0x140002c07  mov     cl, [rax+4]
0x140002c0a  mov     byte ptr [rsp+2E8h+var_1E4], cl
0x140002c11  mov     byte ptr [rsp+2E8h+var_1E4+1], r14b
0x140002c19  movups  xmm0, cs:FT_MessageGuid
0x140002c20  movdqu  [rsp+2E8h+var_1D4+4], xmm0
0x140002c29  lea     rax, [rsp+2E8h+var_1A8]
0x140002c31  mov     qword ptr [rsp+2E8h+var_1C4+0Ch], rax
0x140002c39  mov     [rsp+2E8h+var_1B0], r14d
0x140002c41  mov     ebx, r14d
0x140002c44  mov     [rsp+2E8h+var_2A4], ebx
0x140002c48  cmp     ebx, 8
0x140002c4b  jge     loc_140002CE3
0x140002c51  movsxd  rax, ebx
0x140002c54  lea     rcx, [rax+rax*4]
0x140002c58  mov     rax, cs:LogSessions
0x140002c5f  mov     edx, [rax+rcx*8+0Ch]
0x140002c63  mov     rax, cs:LogSessions
0x140002c6a  mov     r8d, [rax+rcx*8+14h]
0x140002c6f  lea     rcx, [rax+rcx*8]; int
0x140002c73  mov     rax, [rcx]
0x140002c76  mov     qword ptr [rsp+2E8h+var_1E4+4], rax
0x140002c7e  test    edx, edx
0x140002c80  jz      short loc_140002CDC
0x140002c82  cmp     edx, [rcx+0Ch]
0x140002c85  jnz     short loc_140002CDC
0x140002c87  bt      r8d, edi
0x140002c8b  jnb     short loc_140002CDC
0x140002c8d  mov     r8d, [rcx+20h]
0x140002c91  bt      r8d, 1Ah
0x140002c96  jb      short loc_140002CA6
0x140002c98  mov     rax, [rsp+2E8h+Context]
0x140002c9d  test    [rax+1E0h], r8d
0x140002ca4  jz      short loc_140002CDC
0x140002ca6  lea     rax, [rsp+2E8h+P]
0x140002cab  mov     [rsp+2E8h+Size], rax; Size
0x140002cb0  lea     r9, [rsp+2E8h+var_2A8]; int
0x140002cb5  lea     r8, [rsp+2E8h+var_2B8]; int
0x140002cba  lea     rdx, [rsp+2E8h+var_298]; int
0x140002cbf  call    FormatFileTraceEvent
0x140002cc4  test    al, al
0x140002cc6  jz      short loc_140002CE3
0x140002cc8  lea     rcx, [rsp+2E8h+WnodeEventItem]; WnodeEventItem
0x140002cd0  call    cs:__imp_IoWMIWriteEvent
0x140002cd7  nop     dword ptr [rax+rax+00h]
0x140002cdc  inc     ebx
0x140002cde  jmp     loc_140002C44
0x140002ce3  mov     rcx, [rsp+2E8h+Context]; Context
0x140002ce8  test    rcx, rcx
0x140002ceb  jz      short loc_140002CF9
0x140002ced  call    cs:__imp_FltReleaseContext
0x140002cf4  nop     dword ptr [rax+rax+00h]
0x140002cf9  mov     ecx, [rsp+2E8h+var_2B8]
0x140002cfd  sub     ecx, 1
0x140002d00  jz      short loc_140002D1F
0x140002d02  cmp     ecx, 1
0x140002d05  jnz     short loc_140002D37
0x140002d07  mov     edx, 72744C46h; Tag
0x140002d0c  mov     rcx, [rsp+2E8h+P]; P
0x140002d11  call    cs:__imp_ExFreePoolWithTag
0x140002d18  nop     dword ptr [rax+rax+00h]
0x140002d1d  jmp     short loc_140002D37
0x140002d1f  mov     rdx, [rsp+2E8h+P]; Entry
0x140002d24  lea     rcx, Lookaside; Lookaside
0x140002d2b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140002d32  nop     dword ptr [rax+rax+00h]
0x140002d37  mov     eax, 1
0x140002d3c  mov     rcx, [rsp+2E8h+var_28]
0x140002d44  xor     rcx, rsp; StackCookie
0x140002d47  call    __security_check_cookie
0x140002d4c  mov     rbx, [rsp+2E8h+arg_10]
0x140002d54  add     rsp, 2D0h
0x140002d5b  pop     r14
0x140002d5d  pop     rdi
0x140002d5e  pop     rsi
0x140002d5f  retn
0x140003feb  push    rbp
0x140003fed  sub     rsp, 30h
0x140003ff1  mov     rbp, rdx
0x140003ff4  mov     rcx, [rbp+70h]; Context
0x140003ff8  test    rcx, rcx
0x140003ffb  jz      short loc_14000400A
0x140003ffd  call    cs:__imp_FltReleaseContext
0x140004004  nop     dword ptr [rax+rax+00h]
0x140004009  nop
0x14000400a  mov     ecx, [rbp+30h]
0x14000400d  sub     ecx, 1
0x140004010  jz      short loc_14000402E
0x140004012  cmp     ecx, 1
0x140004015  jnz     short loc_140004046
0x140004017  mov     edx, 72744C46h; Tag
0x14000401c  mov     rcx, [rbp+38h]; P
0x140004020  call    cs:__imp_ExFreePoolWithTag
0x140004027  nop     dword ptr [rax+rax+00h]
0x14000402c  jmp     short loc_140004046
0x14000402e  mov     rdx, [rbp+38h]; Entry
0x140004032  lea     rcx, Lookaside; Lookaside
0x140004039  call    cs:__imp_ExFreeToNPagedLookasideList
0x140004040  nop     dword ptr [rax+rax+00h]
0x140004045  nop
0x140004046  add     rsp, 30h
0x14000404a  pop     rbp
0x14000404b  retn
```
