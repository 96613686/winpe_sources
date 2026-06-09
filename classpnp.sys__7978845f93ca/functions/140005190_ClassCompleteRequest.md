# ClassCompleteRequest

- ea: `0x140005190`
- end: `0x140005557`
- name: `ClassCompleteRequest`
- size: `967`
- prototype: `void __stdcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, CCHAR PriorityBoost)`
- caller_count: `58`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400029d0`
- `0x14000cab0`
- `0x140010400`
- `0x140011ba0`
- `0x140012a00`
- `0x140012e40`
- `0x140012f10`
- `0x140013000`
- `0x140013240`
- `0x140013690`
- `0x140014418`
- `0x14001522c`
- `0x140015710`
- `0x1400171d0`
- `0x140019de0`
- `0x14001c9e0`
- `0x14001ccb0`
- `0x14001e86c`
- `0x14001ecc0`
- `0x140020278`
- `0x140023020`
- `0x140023e3c`
- `0x140025f80`
- `0x140028ee0`
- `0x14002a47c`
- `0x14002a8d0`
- `0x14002b450`
- `0x14002cf20`
- `0x14002d800`
- `0x14002e3f0`
- `0x14002f308`
- `0x14002f7f4`
- `0x14002f9fc`
- `0x14002fdd8`
- `0x140030338`
- `0x140030be8`
- `0x1400319bc`
- `0x140031d6c`
- `0x1400320dc`
- `0x140032444`
- `0x1400327ac`
- `0x140032d74`
- `0x140033924`
- `0x140033d94`
- `0x1400340b4`
- `0x1400344a8`
- `0x1400347bc`
- `0x140034e08`
- `0x140035128`
- `0x140035764`

## callees

- `0x140005190`
- `0x140005560`
- `0x1400180f4`
- `0x140018180`
- `0x14002249c`
- `0x14003c278`
- `0x14003c914`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x1400051df`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400051df`
- `ntoskrnl!IofCompleteRequest` at `0x140005210`
- `ntoskrnl!IofCompleteRequest` at `0x140005210`

## pseudocode

```c
void __stdcall ClassCompleteRequest(PDEVICE_OBJECT DeviceObject, PIRP Irp, CCHAR PriorityBoost)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  int MajorFunction; // ecx
  int v8; // ecx
  int v9; // ecx
  NTSTATUS Status; // ecx
  _BYTE *DeviceExtension; // rsi
  bool v12; // zf
  unsigned int LowPart; // r13d
  __int128 *v14; // rax
  __int64 v15; // r10
  _DWORD *v16; // rdx
  __int64 v17; // r11
  __int64 v18; // rbp
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned int v21; // r15d
  int v22; // r14d
  __int64 v23; // r9
  int v24; // r14d
  __int64 v25; // r9
  int v26; // r14d
  __int64 v27; // r9
  char *v28; // r14
  int v29; // ecx
  int v30; // ecx
  __int128 v31; // [rsp+70h] [rbp-68h] BYREF
  __int128 v32; // [rsp+80h] [rbp-58h] BYREF

  if ( !ClassPnPETWEnabled )
    goto LABEL_4;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v31 = 0;
  IoGetActivityIdIrp(Irp, &v31);
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( MajorFunction == 4 || (v8 = MajorFunction - 3) == 0 )
  {
    ClasspWriteIOResultEvent(DeviceObject, 0, Irp);
    goto LABEL_4;
  }
  v9 = v8 - 11;
  if ( !v9 )
  {
    Status = Irp->IoStatus.Status;
    DeviceExtension = DeviceObject->DeviceExtension;
    if ( Status < 0 )
    {
      v12 = (DeviceExtension[104] & 1) == 0;
      v32 = 0;
      if ( !v12 && Status != -1073741306 )
      {
        if ( Status > -1073741808 )
        {
          if ( Status != -1073741789 && Status != -1073741637 )
          {
            v12 = Status == -1073740701;
            goto LABEL_15;
          }
        }
        else if ( Status != -1073741808 && Status != -2147483643 && Status != -1073741822 )
        {
          v12 = Status == -1073741820;
LABEL_15:
          if ( !v12 )
          {
            if ( (LowPart = Irp->Tail.Overlay.CurrentStackLocation->Parameters.Read.ByteOffset.LowPart,
                  LowPart != 2954240)
              && LowPart != 2956288
              && LowPart != 475264
              || Status != -1073741823 )
            {
              v14 = (__int128 *)*((_QWORD *)DeviceExtension + 146);
              v15 = 0;
              v16 = (_DWORD *)*((_QWORD *)DeviceExtension + 65);
              v17 = 0;
              v18 = 0;
              v19 = 0;
              if ( v14 )
                LODWORD(v14) = (_DWORD)v14 + 4;
              else
                v14 = &v32;
              if ( v16 )
              {
                v20 = (unsigned int)v16[3];
                v21 = v16[1];
                if ( (_DWORD *)((char *)v16 + v20) < v16 )
                {
                  v22 = 0;
                }
                else
                {
                  v22 = v21 - v20;
                  if ( (unsigned int)v20 > v21 )
                    v22 = 0;
                }
                if ( (_DWORD)v20 && v22 )
                  v15 = (__int64)v16 + v20;
                v23 = (unsigned int)v16[4];
                if ( (_DWORD *)((char *)v16 + v23) < v16 )
                {
                  v24 = 0;
                }
                else
                {
                  v24 = v21 - v23;
                  if ( (unsigned int)v23 > v21 )
                    v24 = 0;
                }
                if ( (_DWORD)v23 && v24 )
                  v17 = (__int64)v16 + v23;
                v25 = (unsigned int)v16[5];
                if ( (_DWORD *)((char *)v16 + v25) < v16 )
                {
                  v26 = 0;
                }
                else
                {
                  v26 = v21 - v25;
                  if ( (unsigned int)v25 > v21 )
                    v26 = 0;
                }
                if ( (_DWORD)v25 && v26 )
                  v18 = (__int64)v16 + v25;
                v27 = (unsigned int)v16[6];
                v28 = (char *)v16 + v27;
                if ( (_DWORD *)((char *)v16 + v27) < v16 )
                {
                  LODWORD(v16) = 0;
                }
                else
                {
                  LODWORD(v16) = v21 - v27;
                  if ( (unsigned int)v27 > v21 )
                    LODWORD(v16) = 0;
                }
                if ( (_DWORD)v27 && (_DWORD)v16 )
                  v19 = (__int64)v28;
              }
              if ( (BYTE3(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 4) != 0 )
                McTemplateK0jqssssdd_EtwWriteTransfer(
                  Status,
                  (_DWORD)v16,
                  (unsigned int)&v31,
                  (_DWORD)v14,
                  *((_DWORD *)DeviceExtension + 147),
                  v15,
                  v17,
                  v18,
                  v19,
                  Status,
                  LowPart);
            }
          }
        }
      }
    }
    if ( (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 4) != 0 )
      McTemplateK0qpd_EtwWriteTransfer(
        Status,
        (unsigned int)EventNonReadWriteRequestComplete,
        (unsigned int)&v31,
        *((_DWORD *)DeviceExtension + 147),
        (char)Irp,
        Irp->IoStatus.Status);
    goto LABEL_4;
  }
  v29 = v9 - 8;
  if ( v29 )
  {
    v30 = v29 - 1;
    if ( v30 )
    {
      if ( v30 == 4 )
        ClasspWritePnPResultEvent(&v31, DeviceObject, Irp);
    }
    else if ( CurrentStackLocation->MinorFunction <= 9u
           && Irp->IoStatus.Status < 0
           && (*((_BYTE *)DeviceObject->DeviceExtension + 104) & 1) != 0 )
    {
      ClasspWriteWMIFailureEvent(&v31, DeviceObject, Irp);
    }
  }
  else
  {
    ClasspWritePowerResultEvent(&v31, DeviceObject, Irp);
  }
LABEL_4:
  IofCompleteRequest(Irp, PriorityBoost);
}

```

## disassembly

```asm
0x140005190  push    rbx
0x140005192  push    rsi
0x140005193  push    rdi
0x140005194  sub     rsp, 0C0h
0x14000519b  mov     rax, cs:__security_cookie
0x1400051a2  xor     rax, rsp
0x1400051a5  mov     [rsp+0D8h+var_48], rax
0x1400051ad  cmp     cs:ClassPnPETWEnabled, 0
0x1400051b4  movzx   edi, r8b
0x1400051b8  mov     rbx, rdx
0x1400051bb  mov     rsi, rcx
0x1400051be  jz      short loc_140005209
0x1400051c0  xorps   xmm0, xmm0
0x1400051c3  mov     [rsp+0D8h+arg_18], rbp
0x1400051cb  mov     rbp, [rdx+0B8h]
0x1400051d2  mov     rcx, rbx
0x1400051d5  lea     rdx, [rsp+0D8h+var_68]
0x1400051da  movups  [rsp+0D8h+var_68], xmm0
0x1400051df  call    cs:__imp_IoGetActivityIdIrp
0x1400051e6  nop     dword ptr [rax+rax+00h]
0x1400051eb  movzx   ecx, byte ptr [rbp+0]
0x1400051ef  cmp     ecx, 4
0x1400051f2  jnz     short loc_140005238
0x1400051f4  mov     r8, rbx
0x1400051f7  xor     edx, edx
0x1400051f9  mov     rcx, rsi
0x1400051fc  call    ClasspWriteIOResultEvent
0x140005201  mov     rbp, [rsp+0D8h+arg_18]
0x140005209  movzx   edx, dil; PriorityBoost
0x14000520d  mov     rcx, rbx; Irp
0x140005210  call    cs:__imp_IofCompleteRequest
0x140005217  nop     dword ptr [rax+rax+00h]
0x14000521c  mov     rcx, [rsp+0D8h+var_48]
0x140005224  xor     rcx, rsp; StackCookie
0x140005227  call    __security_check_cookie
0x14000522c  add     rsp, 0C0h
0x140005233  pop     rdi
0x140005234  pop     rsi
0x140005235  pop     rbx
0x140005236  retn
0x140005238  sub     ecx, 3
0x14000523b  jz      short loc_1400051F4
0x14000523d  sub     ecx, 0Bh
0x140005240  jnz     loc_14000546B
0x140005246  mov     ecx, [rbx+30h]
0x140005249  mov     rsi, [rsi+40h]
0x14000524d  test    ecx, ecx
0x14000524f  jns     loc_14000540E
0x140005255  test    byte ptr [rsi+68h], 1
0x140005259  xorps   xmm0, xmm0
0x14000525c  movups  [rsp+0D8h+var_58], xmm0
0x140005264  jz      loc_14000540E
0x14000526a  cmp     ecx, 0C0000206h
0x140005270  jz      loc_14000540E
0x140005276  cmp     ecx, 0C0000010h
0x14000527c  jg      loc_140005444
0x140005282  jz      loc_14000540E
0x140005288  cmp     ecx, 80000005h
0x14000528e  jz      loc_14000540E
0x140005294  cmp     ecx, 0C0000002h
0x14000529a  jz      loc_14000540E
0x1400052a0  cmp     ecx, 0C0000004h
0x1400052a6  jz      loc_14000540E
0x1400052ac  mov     rax, [rbx+0B8h]
0x1400052b3  mov     [rsp+0D8h+var_28], r13
0x1400052bb  mov     r13d, [rax+18h]
0x1400052bf  cmp     r13d, 2D1400h
0x1400052c6  jz      loc_14000550B
0x1400052cc  cmp     r13d, 2D1C00h
0x1400052d3  jz      loc_14000550B
0x1400052d9  cmp     r13d, 74080h
0x1400052e0  jz      loc_14000550B
0x1400052e6  mov     rax, [rsi+490h]
0x1400052ed  xor     r10d, r10d
0x1400052f0  mov     rdx, [rsi+208h]
0x1400052f7  xor     r11d, r11d
0x1400052fa  xor     ebp, ebp
0x1400052fc  xor     r8d, r8d
0x1400052ff  test    rax, rax
0x140005302  jz      loc_1400054DF
0x140005308  add     rax, 4
0x14000530c  mov     [rsp+0D8h+var_70], rax
0x140005311  test    rdx, rdx
0x140005314  jz      loc_1400053F9
0x14000531a  mov     r9d, [rdx+0Ch]
0x14000531e  mov     [rsp+0D8h+var_20], r12
0x140005326  mov     [rsp+0D8h+var_30], r14
0x14000532e  mov     [rsp+0D8h+var_38], r15
0x140005336  mov     r15d, [rdx+4]
0x14000533a  lea     r12, [r9+rdx]
0x14000533e  cmp     r12, rdx
0x140005341  jb      loc_1400054EC
0x140005347  xor     eax, eax
0x140005349  mov     r14d, r15d
0x14000534c  sub     r14d, r9d
0x14000534f  cmp     r9d, r15d
0x140005352  cmova   r14d, eax
0x140005356  test    r9d, r9d
0x140005359  jnz     loc_14000545F
0x14000535f  mov     r9d, [rdx+10h]
0x140005363  lea     r12, [r9+rdx]
0x140005367  cmp     r12, rdx
0x14000536a  jb      loc_1400054F4
0x140005370  xor     eax, eax
0x140005372  mov     r14d, r15d
0x140005375  sub     r14d, r9d
0x140005378  cmp     r9d, r15d
0x14000537b  cmova   r14d, eax
0x14000537f  test    r9d, r9d
0x140005382  jz      short loc_14000538B
0x140005384  test    r14d, r14d
0x140005387  cmovnz  r11, r12
0x14000538b  mov     r9d, [rdx+14h]
0x14000538f  lea     r12, [r9+rdx]
0x140005393  cmp     r12, rdx
0x140005396  jb      loc_1400054FC
0x14000539c  xor     eax, eax
0x14000539e  mov     r14d, r15d
0x1400053a1  sub     r14d, r9d
0x1400053a4  cmp     r9d, r15d
0x1400053a7  cmova   r14d, eax
0x1400053ab  test    r9d, r9d
0x1400053ae  jz      short loc_1400053B7
0x1400053b0  test    r14d, r14d
0x1400053b3  cmovnz  rbp, r12
0x1400053b7  mov     r9d, [rdx+18h]
0x1400053bb  mov     r12, [rsp+0D8h+var_20]
0x1400053c3  lea     r14, [r9+rdx]
0x1400053c7  cmp     r14, rdx
0x1400053ca  jb      loc_140005504
0x1400053d0  xor     eax, eax
0x1400053d2  mov     edx, r15d
0x1400053d5  sub     edx, r9d
0x1400053d8  cmp     r9d, r15d
0x1400053db  cmova   edx, eax
0x1400053de  mov     r15, [rsp+0D8h+var_38]
0x1400053e6  test    r9d, r9d
0x1400053e9  jz      short loc_1400053F1
0x1400053eb  test    edx, edx
0x1400053ed  cmovnz  r8, r14
0x1400053f1  mov     r14, [rsp+0D8h+var_30]
0x1400053f9  test    byte ptr cs:WPP_MAIN_CB.Queue+3Bh, 4
0x140005400  jnz     loc_14000551C
0x140005406  mov     r13, [rsp+0D8h+var_28]
0x14000540e  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 4
0x140005415  jz      loc_140005201
0x14000541b  mov     eax, [rbx+30h]
0x14000541e  lea     r8, [rsp+0D8h+var_68]
0x140005423  mov     r9d, [rsi+24Ch]
0x14000542a  lea     rdx, EventNonReadWriteRequestComplete
0x140005431  mov     dword ptr [rsp+0D8h+var_B0], eax
0x140005435  mov     [rsp+0D8h+var_B8], rbx
0x14000543a  call    McTemplateK0qpd_EtwWriteTransfer
0x14000543f  jmp     loc_140005201
0x140005444  cmp     ecx, 0C0000023h
0x14000544a  jz      short loc_14000540E
0x14000544c  cmp     ecx, 0C00000BBh
0x140005452  jz      short loc_14000540E
0x140005454  cmp     ecx, 0C0000463h
0x14000545a  jmp     loc_1400052A6
0x14000545f  test    r14d, r14d
0x140005462  cmovnz  r10, r12
0x140005466  jmp     loc_14000535F
0x14000546b  sub     ecx, 8
0x14000546e  jz      short loc_140005493
0x140005470  sub     ecx, 1
0x140005473  jz      short loc_1400054A8
0x140005475  cmp     ecx, 4
0x140005478  jnz     loc_140005201
0x14000547e  mov     r8, rbx
0x140005481  lea     rcx, [rsp+0D8h+var_68]
0x140005486  mov     rdx, rsi
0x140005489  call    ClasspWritePnPResultEvent
0x14000548e  jmp     loc_140005201
0x140005493  mov     r8, rbx
0x140005496  lea     rcx, [rsp+0D8h+var_68]
0x14000549b  mov     rdx, rsi
0x14000549e  call    ClasspWritePowerResultEvent
0x1400054a3  jmp     loc_140005201
0x1400054a8  cmp     byte ptr [rbp+1], 9
0x1400054ac  ja      loc_140005201
0x1400054b2  cmp     dword ptr [rbx+30h], 0
0x1400054b6  jge     loc_140005201
0x1400054bc  mov     rax, [rsi+40h]
0x1400054c0  test    byte ptr [rax+68h], 1
0x1400054c4  jz      loc_140005201
0x1400054ca  mov     r8, rbx
0x1400054cd  lea     rcx, [rsp+0D8h+var_68]
0x1400054d2  mov     rdx, rsi
0x1400054d5  call    ClasspWriteWMIFailureEvent
0x1400054da  jmp     loc_140005201
0x1400054df  lea     rax, [rsp+0D8h+var_58]
0x1400054e7  jmp     loc_14000530C
0x1400054ec  xor     r14d, r14d
0x1400054ef  jmp     loc_140005356
0x1400054f4  xor     r14d, r14d
0x1400054f7  jmp     loc_14000537F
0x1400054fc  xor     r14d, r14d
0x1400054ff  jmp     loc_1400053AB
0x140005504  xor     edx, edx
0x140005506  jmp     loc_1400053DE
0x14000550b  cmp     ecx, 0C0000001h
0x140005511  jz      loc_140005406
0x140005517  jmp     loc_1400052E6
0x14000551c  mov     eax, [rsi+24Ch]
0x140005522  mov     r9, [rsp+0D8h+var_70]
0x140005527  mov     [rsp+0D8h+var_88], r13d
0x14000552c  mov     [rsp+0D8h+var_90], ecx
0x140005530  mov     [rsp+0D8h+var_98], r8
0x140005535  lea     r8, [rsp+0D8h+var_68]
0x14000553a  mov     [rsp+0D8h+var_A0], rbp
0x14000553f  mov     [rsp+0D8h+var_A8], r11
0x140005544  mov     [rsp+0D8h+var_B0], r10
0x140005549  mov     dword ptr [rsp+0D8h+var_B8], eax
0x14000554d  call    McTemplateK0jqssssdd_EtwWriteTransfer
0x140005552  jmp     loc_140005406
```
