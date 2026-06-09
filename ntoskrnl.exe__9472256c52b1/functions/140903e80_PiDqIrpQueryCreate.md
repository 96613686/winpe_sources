# PiDqIrpQueryCreate

- ea: `0x140903e80`
- end: `0x140904185`
- name: `PiDqIrpQueryCreate`
- size: `773`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140903cb0`

## callees

- `0x140465490`
- `0x14046c860`
- `0x1406dc8c0`
- `0x1409034e8`
- `0x140903640`
- `0x140903e80`
- `0x140904bd0`
- `0x140904c40`
- `0x140904ca0`
- `0x140904e40`
- `0x140904ee0`
- `0x140905024`
- `0x1409051b4`

## import_xrefs

- `msrpc!MesDecodeBufferHandleCreate` at `0x140903f75`
- `msrpc!MesDecodeBufferHandleCreate` at `0x140903f75`
- `msrpc!RpcExceptionFilter` at `0x140b446ea`
- `msrpc!RpcExceptionFilter` at `0x140b446ea`
- `msrpc!NdrMesTypeDecode3` at `0x140903fb2`
- `msrpc!NdrMesTypeDecode3` at `0x140903fb2`

## pseudocode

```c
__int64 __fastcall PiDqIrpQueryCreate(PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  __int64 v3; // rbx
  __int64 v4; // r14
  char v5; // r15
  union _IRP::$CBBBB9F4F0755A16DC8A369061485BEC *p_AssociatedIrp; // r15
  int *v7; // r14
  int v8; // eax
  int v9; // eax
  int ValidateQueryData; // edi
  unsigned int Length; // r8d
  char v13; // [rsp+30h] [rbp-A8h]
  char v14; // [rsp+31h] [rbp-A7h]
  int v15; // [rsp+34h] [rbp-A4h] BYREF
  unsigned int v16; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+40h] [rbp-98h]
  __int64 v18; // [rsp+48h] [rbp-90h]
  __int64 v19; // [rsp+50h] [rbp-88h]
  PIRP v20; // [rsp+58h] [rbp-80h]
  struct _IO_STACK_LOCATION *v21; // [rsp+60h] [rbp-78h]
  _DWORD *FsContext2; // [rsp+68h] [rbp-70h]
  union _IRP::$CBBBB9F4F0755A16DC8A369061485BEC *v23; // [rsp+70h] [rbp-68h]
  char *v24; // [rsp+78h] [rbp-60h]
  __int128 v25; // [rsp+80h] [rbp-58h] BYREF
  __int128 v26; // [rsp+90h] [rbp-48h] BYREF

  v20 = Irp;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v21 = CurrentStackLocation;
  FsContext2 = CurrentStackLocation->FileObject->FsContext2;
  v3 = (__int64)FsContext2;
  v14 = 0;
  v4 = 0;
  v17 = 0;
  v19 = 0;
  v25 = 0;
  v5 = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v26 = 0;
  if ( FsContext2 )
  {
    p_AssociatedIrp = &Irp->AssociatedIrp;
    v23 = &Irp->AssociatedIrp;
    if ( Irp->AssociatedIrp.MasterIrp )
    {
      PiDqQueryLock(FsContext2);
      v7 = FsContext2 + 54;
      v24 = (char *)(FsContext2 + 54);
      v8 = FsContext2[54];
      if ( (v8 & 8) != 0 )
      {
        ValidateQueryData = -1073741536;
      }
      else if ( (v8 & 0x10) != 0 || (v9 = v8 | 0x10, *v7 = v9, v14 = 1, (v9 & 4) != 0) )
      {
        ValidateQueryData = -1073741637;
      }
      else if ( CurrentStackLocation->Parameters.Read.Length < 0x10 )
      {
        ValidateQueryData = -1073741789;
      }
      else
      {
        v18 = v3;
        ValidateQueryData = MesDecodeBufferHandleCreate(
                              p_AssociatedIrp->MasterIrp,
                              CurrentStackLocation->Parameters.Create.Options,
                              v3 + 16);
        if ( ValidateQueryData >= 0 )
        {
          NdrMesTypeDecode3(*(_QWORD *)(v3 + 16), "TP 3\a", &off_140004F50, &off_140E0A510, 0, v3 + 24);
          ValidateQueryData = PiDqQueryValidateQueryData(*(_QWORD *)(v3 + 24));
          if ( ValidateQueryData >= 0 )
          {
            if ( !(unsigned __int8)PnpIsNullGuid(*(void **)(v3 + 24)) )
            {
              v25 = *(_OWORD *)*(_QWORD *)(v3 + 24);
              v17 = IoSetActivityIdThread(&v25);
              v13 = 1;
            }
            PiDqTraceQueryCreate(v3);
            *v7 |= 4u;
          }
        }
      }
      PiDqQueryUnlock(v3);
      if ( ValidateQueryData >= 0 )
      {
        Length = CurrentStackLocation->Parameters.Read.Length;
        if ( Length > 0x10 )
          ValidateQueryData = PiDqQuerySerializeActionQueue(
                                v3,
                                p_AssociatedIrp->MasterIrp,
                                Length,
                                CurrentStackLocation->Parameters.Read.ByteOffset.LowPart,
                                (__int64)&v15,
                                (__int64)&v16);
      }
      v4 = v17;
      v5 = v13;
    }
    else
    {
      ValidateQueryData = -1073741811;
      v5 = 0;
    }
  }
  else
  {
    ValidateQueryData = -1073741637;
  }
  if ( v14 )
  {
    PiDqQueryLock(v3);
    if ( ValidateQueryData < 0 )
    {
      *(_DWORD *)(v3 + 216) |= 1u;
      PiDqQueryFreeActiveData(v3);
    }
    else
    {
      PiDqQueryGetNextIoctlInfo(v3, CurrentStackLocation->Parameters.Read.Length, v16, &v26);
    }
    *(_DWORD *)(v3 + 216) &= ~0x10u;
    PiDqQueryUnlock(v3);
  }
  PiDqIrpComplete(Irp);
  if ( v5 )
    IoClearActivityIdThread(v4);
  return (unsigned int)ValidateQueryData;
}

```

## disassembly

```asm
0x140903e80  mov     r11, rsp
0x140903e83  mov     [r11+10h], rbx
0x140903e87  mov     [r11+18h], rsi
0x140903e8b  push    rdi
0x140903e8c  push    r12
0x140903e8e  push    r13
0x140903e90  push    r14
0x140903e92  push    r15
0x140903e94  sub     rsp, 0B0h
0x140903e9b  mov     rax, cs:__security_cookie
0x140903ea2  xor     rax, rsp
0x140903ea5  mov     [rsp+0D8h+var_38], rax
0x140903ead  mov     r13, rcx
0x140903eb0  mov     [rsp+0D8h+var_80], rcx
0x140903eb5  mov     rsi, [rcx+0B8h]
0x140903ebc  mov     [rsp+0D8h+var_78], rsi
0x140903ec1  mov     rax, [rsi+30h]
0x140903ec5  mov     rbx, [rax+20h]
0x140903ec9  mov     [rsp+0D8h+var_70], rbx
0x140903ece  mov     [rsp+0D8h+var_A7], 0
0x140903ed3  xor     r14d, r14d
0x140903ed6  mov     [rsp+0D8h+var_98], r14
0x140903edb  mov     [rsp+0D8h+var_88], r14
0x140903ee0  xorps   xmm0, xmm0
0x140903ee3  movups  xmmword ptr [r11-58h], xmm0
0x140903ee8  xor     r15b, r15b
0x140903eeb  mov     [rsp+0D8h+var_A8], r15b
0x140903ef0  xor     r12d, r12d
0x140903ef3  mov     [rsp+0D8h+var_A4], r12d
0x140903ef8  mov     [rsp+0D8h+var_A0], r12d
0x140903efd  movups  xmmword ptr [r11-48h], xmm0
0x140903f02  test    rbx, rbx
0x140903f05  jz      loc_14090413F
0x140903f0b  lea     r15, [rcx+18h]
0x140903f0f  mov     [rsp+0D8h+var_68], r15
0x140903f14  cmp     [r15], r12
0x140903f17  jz      loc_140904153
0x140903f1d  mov     rcx, rbx
0x140903f20  call    PiDqQueryLock
0x140903f25  lea     r14, [rbx+0D8h]
0x140903f2c  mov     [rsp+0D8h+var_60], r14
0x140903f31  mov     eax, [r14]
0x140903f34  test    al, 8
0x140903f36  jnz     loc_140904149
0x140903f3c  test    al, 10h
0x140903f3e  jnz     loc_140904160
0x140903f44  or      eax, 10h
0x140903f47  mov     [r14], eax
0x140903f4a  mov     cl, 1
0x140903f4c  mov     [rsp+0D8h+var_A7], cl
0x140903f50  mov     [rsp+0D8h+var_A6], cl
0x140903f54  test    al, 4
0x140903f56  jnz     loc_140904160
0x140903f5c  cmp     dword ptr [rsi+8], 10h
0x140903f60  jb      loc_14090416A
0x140903f66  mov     [rsp+0D8h+var_90], rbx
0x140903f6b  lea     r8, [rbx+10h]
0x140903f6f  mov     edx, [rsi+10h]
0x140903f72  mov     rcx, [r15]
0x140903f75  call    cs:__imp_MesDecodeBufferHandleCreate
0x140903f7c  nop     dword ptr [rax+rax+00h]
0x140903f81  mov     edi, eax
0x140903f83  test    eax, eax
0x140903f85  js      loc_140904056
0x140903f8b  lea     rax, [rbx+18h]
0x140903f8f  mov     [rsp+0D8h+var_B0], rax
0x140903f94  mov     dword ptr [rsp+0D8h+var_B8], r12d
0x140903f99  lea     r9, off_140E0A510
0x140903fa0  lea     r8, off_140004F50
0x140903fa7  lea     rdx, aTp3; "TP 3\a"
0x140903fae  mov     rcx, [rbx+10h]
0x140903fb2  call    cs:__imp_NdrMesTypeDecode3
0x140903fb9  nop     dword ptr [rax+rax+00h]
0x140903fbe  jmp     short loc_140904003
0x140903fc0  mov     edi, eax
0x140903fc2  mov     rax, [rsp+0D8h+var_90]
0x140903fc7  mov     qword ptr [rax+18h], 0
0x140903fcf  mov     al, [rsp+0D8h+var_A6]
0x140903fd3  mov     [rsp+0D8h+var_A7], al
0x140903fd7  mov     rax, [rsp+0D8h+var_88]
0x140903fdc  mov     [rsp+0D8h+var_98], rax
0x140903fe1  mov     [rsp+0D8h+var_A8], al
0x140903fe5  mov     r12d, [rsp+0D8h+var_A4]
0x140903fea  mov     r13, [rsp+0D8h+var_80]
0x140903fef  mov     rsi, [rsp+0D8h+var_78]
0x140903ff4  mov     rbx, [rsp+0D8h+var_70]
0x140903ff9  mov     r15, [rsp+0D8h+var_68]
0x140903ffe  mov     r14, [rsp+0D8h+var_60]
0x140904003  test    edi, edi
0x140904005  js      short loc_140904056
0x140904007  mov     rcx, [rbx+18h]
0x14090400b  call    PiDqQueryValidateQueryData
0x140904010  mov     edi, eax
0x140904012  test    eax, eax
0x140904014  js      short loc_140904056
0x140904016  mov     rcx, [rbx+18h]; Source2
0x14090401a  call    PnpIsNullGuid
0x14090401f  test    al, al
0x140904021  jnz     short loc_14090404A
0x140904023  mov     rax, [rbx+18h]
0x140904027  movups  xmm0, xmmword ptr [rax]
0x14090402a  movdqu  [rsp+0D8h+var_58], xmm0
0x140904033  lea     rcx, [rsp+0D8h+var_58]
0x14090403b  call    IoSetActivityIdThread
0x140904040  mov     [rsp+0D8h+var_98], rax
0x140904045  mov     [rsp+0D8h+var_A8], 1
0x14090404a  mov     rcx, rbx
0x14090404d  call    PiDqTraceQueryCreate
0x140904052  or      dword ptr [r14], 4
0x140904056  mov     rcx, rbx
0x140904059  call    PiDqQueryUnlock
0x14090405e  test    edi, edi
0x140904060  js      short loc_14090409A
0x140904062  mov     r8d, [rsi+8]
0x140904066  cmp     r8d, 10h
0x14090406a  jbe     loc_140904134
0x140904070  lea     rax, [rsp+0D8h+var_A0]
0x140904075  mov     [rsp+0D8h+var_B0], rax
0x14090407a  lea     rax, [rsp+0D8h+var_A4]
0x14090407f  mov     [rsp+0D8h+var_B8], rax
0x140904084  mov     r9d, [rsi+18h]
0x140904088  mov     rdx, [r15]
0x14090408b  mov     rcx, rbx
0x14090408e  call    PiDqQuerySerializeActionQueue
0x140904093  mov     edi, eax
0x140904095  mov     r12d, [rsp+0D8h+var_A4]
0x14090409a  mov     r14, [rsp+0D8h+var_98]
0x14090409f  mov     r15b, [rsp+0D8h+var_A8]
0x1409040a4  cmp     [rsp+0D8h+var_A7], 0
0x1409040a9  jz      short loc_1409040E2
0x1409040ab  mov     rcx, rbx
0x1409040ae  call    PiDqQueryLock
0x1409040b3  mov     rcx, rbx
0x1409040b6  test    edi, edi
0x1409040b8  js      loc_140904174
0x1409040be  lea     r9, [rsp+0D8h+var_48]
0x1409040c6  mov     r8d, [rsp+0D8h+var_A0]
0x1409040cb  mov     edx, [rsi+8]
0x1409040ce  call    PiDqQueryGetNextIoctlInfo
0x1409040d3  and     dword ptr [rbx+0D8h], 0FFFFFFEFh
0x1409040da  mov     rcx, rbx
0x1409040dd  call    PiDqQueryUnlock
0x1409040e2  lea     r9, [rsp+0D8h+var_48]
0x1409040ea  mov     r8d, r12d
0x1409040ed  mov     edx, edi
0x1409040ef  mov     rcx, r13; Irp
0x1409040f2  call    PiDqIrpComplete
0x1409040f7  test    r15b, r15b
0x1409040fa  jz      short loc_140904104
0x1409040fc  mov     rcx, r14
0x1409040ff  call    IoClearActivityIdThread
0x140904104  mov     eax, edi
0x140904106  mov     rcx, [rsp+0D8h+var_38]
0x14090410e  xor     rcx, rsp; StackCookie
0x140904111  call    __security_check_cookie
0x140904116  lea     r11, [rsp+0D8h+var_28]
0x14090411e  mov     rbx, [r11+38h]
0x140904122  mov     rsi, [r11+40h]
0x140904126  mov     rsp, r11
0x140904129  pop     r15
0x14090412b  pop     r14
0x14090412d  pop     r13
0x14090412f  pop     r12
0x140904131  pop     rdi
0x140904132  retn
0x140904134  mov     r12d, 10h
0x14090413a  jmp     loc_14090409A
0x14090413f  mov     edi, 0C00000BBh
0x140904144  jmp     loc_1409040A4
0x140904149  mov     edi, 0C0000120h
0x14090414e  jmp     loc_140904056
0x140904153  mov     edi, 0C000000Dh
0x140904158  xor     r15b, r15b
0x14090415b  jmp     loc_1409040A4
0x140904160  mov     edi, 0C00000BBh
0x140904165  jmp     loc_140904056
0x14090416a  mov     edi, 0C0000023h
0x14090416f  jmp     loc_140904056
0x140904174  or      dword ptr [rbx+0D8h], 1
0x14090417b  call    PiDqQueryFreeActiveData
0x140904180  jmp     loc_1409040D3
0x140b446dc  push    rbp
0x140b446de  sub     rsp, 30h
0x140b446e2  mov     rbp, rdx
0x140b446e5  mov     rcx, [rcx]
0x140b446e8  mov     ecx, [rcx]; ExceptionCode
0x140b446ea  call    cs:__imp_RpcExceptionFilter
0x140b446f1  nop     dword ptr [rax+rax+00h]
0x140b446f6  nop
0x140b446f7  add     rsp, 30h
0x140b446fb  pop     rbp
0x140b446fc  retn
```
