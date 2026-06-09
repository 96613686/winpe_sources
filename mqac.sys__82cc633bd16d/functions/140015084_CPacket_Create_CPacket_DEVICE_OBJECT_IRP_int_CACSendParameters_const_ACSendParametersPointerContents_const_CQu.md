# CPacket::Create(CPacket * *,_DEVICE_OBJECT *,_IRP *,int,CACSendParameters const *,ACSendParametersPointerContents const *,CQueue const *,ulong,QUEUE_FORMAT const * const,bool)

- ea: `0x140015084`
- end: `0x1400152ca`
- name: `?Create@CPacket@@CAJPEAPEAV1@PEAU_DEVICE_OBJECT@@PEAU_IRP@@HPEBVCACSendParameters@@PEBUACSendParametersPointerContents@@PEBVCQueue@@KQEBUQUEUE_FORMAT@@_N@Z`
- size: `582`
- prototype: `__int64 __fastcall(struct CPacket **, struct _DEVICE_OBJECT *, struct _IRP *, int, const struct CACSendParameters *, const struct ACSendParametersPointerContents *, const struct CQueue *, unsigned int, const struct QUEUE_FORMAT *const, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400194ec`

## callees

- `0x140001c34`
- `0x140001cb0`
- `0x14000c6c8`
- `0x140012754`
- `0x140012dc4`
- `0x140013b94`
- `0x140015084`
- `0x1400152d0`
- `0x140017a2c`
- `0x140019674`

## pseudocode

```c
__int64 __fastcall CPacket::Create(
        struct CPacket **a1,
        struct _DEVICE_OBJECT *a2,
        struct _IRP *a3,
        int a4,
        const struct CACSendParameters *a5,
        const struct ACSendParametersPointerContents *a6,
        const struct CQueue *a7,
        unsigned int a8,
        const struct QUEUE_FORMAT *a9,
        char a10)
{
  char v14; // al
  __int64 result; // rax
  struct _DEVICE_OBJECT *v16; // rdx
  __int64 v17; // r9
  int v18; // r11d
  int v19; // eax
  unsigned int v20; // esi
  unsigned int v21; // eax
  int v22; // r9d
  int v23; // eax
  unsigned int v24; // edi
  struct CPacketBuffer *v25; // rax
  int v26; // edi
  __int64 v27[2]; // [rsp+30h] [rbp-68h] BYREF
  char v28; // [rsp+40h] [rbp-58h]
  int v29; // [rsp+42h] [rbp-56h]
  __int64 v30; // [rsp+48h] [rbp-50h]
  int v31; // [rsp+50h] [rbp-48h]
  __int64 v32; // [rsp+58h] [rbp-40h]
  const struct QUEUE_FORMAT *v33; // [rsp+60h] [rbp-38h]
  struct _IRP *v34; // [rsp+68h] [rbp-30h]

  *a1 = 0;
  v14 = a8 > 1 || *(_BYTE *)a9 == 6;
  result = ValidateProperties((_DWORD)a2, (_DWORD)a5, (_DWORD)a6, (_DWORD)a7, a10, v14);
  if ( (int)result >= 0 )
  {
    v27[0] = (__int64)a5;
    v27[1] = (__int64)a6;
    v28 = a10;
    v29 = 0;
    v30 = 0;
    v31 = v18;
    v32 = v17;
    v33 = a9;
    v34 = a3;
    v19 = PacketConstructionParameters::Initialize((PacketConstructionParameters *)v27, v16);
    v20 = v19;
    if ( v19 >= 0 )
    {
      v21 = ACpCalcPacketSize(a2, v27);
      if ( !*((_QWORD *)a5 + 8) || (v22 = 2, (*((_BYTE *)a6 + 17) & 2) == 0) )
        v22 = *((_QWORD *)a5 + 6) && *((_BYTE *)a6 + 16) == 1 || *((_QWORD *)a5 + 45) != 0;
      v23 = CPacket::Create(a1, (__int64)a2, v21, v22, a4);
      v24 = v23;
      if ( v23 >= 0 )
      {
        v25 = CQEntry::Buffer(*a1);
        v26 = ACpBuildPacket((__int64)a2, (__int64)v25, v27);
        if ( v26 >= 0 )
        {
          return 0;
        }
        else
        {
          ACpRelease<CPacket>(*a1);
          *a1 = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->Queue.ListEntry.Blink,
              17,
              WPP_521cf5ef77973c292796e113f00b944d_Traceguids,
              (unsigned int)v26);
          }
          return (unsigned int)v26;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->Queue.ListEntry.Blink,
            16,
            WPP_521cf5ef77973c292796e113f00b944d_Traceguids,
            (unsigned int)v23);
        }
        return v24;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->Queue.ListEntry.Blink,
          15,
          WPP_521cf5ef77973c292796e113f00b944d_Traceguids,
          (unsigned int)v19);
      }
      return v20;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140015084  mov     [rsp+arg_8], rbx
0x140015089  mov     [rsp+arg_10], rsi
0x14001508e  mov     [rsp+arg_0], rcx
0x140015093  push    rdi
0x140015094  push    r12
0x140015096  push    r13
0x140015098  push    r14
0x14001509a  push    r15
0x14001509c  sub     rsp, 70h
0x1400150a0  mov     r13d, r9d
0x1400150a3  mov     r12, r8
0x1400150a6  mov     r15, rdx
0x1400150a9  mov     rbx, rcx
0x1400150ac  mov     qword ptr [rcx], 0
0x1400150b3  mov     r11d, [rsp+98h+arg_38]
0x1400150bb  cmp     r11d, 1
0x1400150bf  ja      short loc_1400150D2
0x1400150c1  mov     rax, [rsp+98h+arg_40]
0x1400150c9  cmp     byte ptr [rax], 6
0x1400150cc  jz      short loc_1400150D2
0x1400150ce  xor     al, al
0x1400150d0  jmp     short loc_1400150D4
0x1400150d2  mov     al, 1
0x1400150d4  mov     [rsp+98h+var_70], al
0x1400150d8  mov     sil, [rsp+98h+arg_48]
0x1400150e0  mov     byte ptr [rsp+98h+var_78], sil
0x1400150e5  mov     r9, [rsp+98h+arg_30]
0x1400150ed  mov     r14, [rsp+98h+arg_28]
0x1400150f5  mov     r8, r14
0x1400150f8  mov     rdi, [rsp+98h+arg_20]
0x140015100  mov     rdx, rdi
0x140015103  mov     rcx, r15
0x140015106  call    ValidateProperties
0x14001510b  test    eax, eax
0x14001510d  js      loc_1400152AF
0x140015113  mov     [rsp+98h+var_68], rdi
0x140015118  mov     [rsp+98h+var_60], r14
0x14001511d  mov     [rsp+98h+var_58], sil
0x140015122  xor     eax, eax
0x140015124  mov     [rsp+98h+var_56], eax
0x140015128  mov     [rsp+98h+var_50], rax
0x14001512d  mov     [rsp+98h+var_48], r11d
0x140015132  mov     [rsp+98h+var_40], r9
0x140015137  mov     rax, [rsp+98h+arg_40]
0x14001513f  mov     [rsp+98h+var_38], rax
0x140015144  mov     [rsp+98h+var_30], r12
0x140015149  lea     rcx, [rsp+98h+var_68]; this
0x14001514e  call    ?Initialize@PacketConstructionParameters@@QEAAJPEAU_DEVICE_OBJECT@@@Z; PacketConstructionParameters::Initialize(_DEVICE_OBJECT *)
0x140015153  mov     esi, eax
0x140015155  xor     r12d, r12d
0x140015158  test    eax, eax
0x14001515a  jns     short loc_140015196
0x14001515c  lea     rdx, WPP_GLOBAL_Control
0x140015163  mov     rcx, cs:WPP_GLOBAL_Control
0x14001516a  cmp     rcx, rdx
0x14001516d  jz      short loc_14001518F
0x14001516f  mov     edx, [rcx+6Ch]
0x140015172  test    dl, 4
0x140015175  jz      short loc_14001518F
0x140015177  lea     edx, [r12+0Fh]
0x14001517c  mov     r9d, eax
0x14001517f  lea     r8, WPP_521cf5ef77973c292796e113f00b944d_Traceguids
0x140015186  mov     rcx, [rcx+58h]
0x14001518a  call    WPP_SF_d
0x14001518f  mov     eax, esi
0x140015191  jmp     loc_1400152AF
0x140015196  lea     rdx, [rsp+98h+var_68]
0x14001519b  mov     rcx, r15
0x14001519e  call    ACpCalcPacketSize
0x1400151a3  cmp     [rdi+40h], r12
0x1400151a7  jz      short loc_1400151B5
0x1400151a9  mov     r9d, 2
0x1400151af  test    [r14+11h], r9b
0x1400151b3  jnz     short loc_1400151D8
0x1400151b5  cmp     [rdi+30h], r12
0x1400151b9  jz      short loc_1400151CA
0x1400151bb  cmp     byte ptr [r14+10h], 1
0x1400151c0  jnz     short loc_1400151CA
0x1400151c2  mov     r9d, 1
0x1400151c8  jmp     short loc_1400151D8
0x1400151ca  mov     r9d, r12d
0x1400151cd  cmp     [rdi+168h], r12
0x1400151d4  setnz   r9b
0x1400151d8  mov     [rsp+98h+var_78], r13d
0x1400151dd  mov     r8d, eax
0x1400151e0  mov     rdx, r15
0x1400151e3  mov     rcx, rbx
0x1400151e6  call    ?Create@CPacket@@SAJPEAPEAV1@PEAU_DEVICE_OBJECT@@KW4ACPoolType@@H@Z; CPacket::Create(CPacket * *,_DEVICE_OBJECT *,ulong,ACPoolType,int)
0x1400151eb  mov     edi, eax
0x1400151ed  test    eax, eax
0x1400151ef  jns     short loc_14001522B
0x1400151f1  lea     rdx, WPP_GLOBAL_Control
0x1400151f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400151ff  cmp     rcx, rdx
0x140015202  jz      short loc_140015224
0x140015204  mov     edx, [rcx+6Ch]
0x140015207  test    dl, 4
0x14001520a  jz      short loc_140015224
0x14001520c  mov     edx, 10h
0x140015211  mov     r9d, eax
0x140015214  lea     r8, WPP_521cf5ef77973c292796e113f00b944d_Traceguids
0x14001521b  mov     rcx, [rcx+58h]
0x14001521f  call    WPP_SF_d
0x140015224  mov     eax, edi
0x140015226  jmp     loc_1400152AF
0x14001522b  mov     rcx, [rbx]; this
0x14001522e  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x140015233  lea     r8, [rsp+98h+var_68]
0x140015238  mov     rdx, rax
0x14001523b  mov     rcx, r15
0x14001523e  call    ACpBuildPacket
0x140015243  mov     edi, eax
0x140015245  test    eax, eax
0x140015247  jns     short loc_14001528B
0x140015249  mov     rcx, [rbx]
0x14001524c  call    ??$ACpRelease@VCPacket@@@@YAXPEAVCPacket@@@Z; ACpRelease<CPacket>(CPacket *)
0x140015251  mov     [rbx], r12
0x140015254  lea     rdx, WPP_GLOBAL_Control
0x14001525b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015262  cmp     rcx, rdx
0x140015265  jz      short loc_140015287
0x140015267  mov     edx, [rcx+6Ch]
0x14001526a  test    dl, 4
0x14001526d  jz      short loc_140015287
0x14001526f  mov     edx, 11h
0x140015274  mov     r9d, edi
0x140015277  lea     r8, WPP_521cf5ef77973c292796e113f00b944d_Traceguids
0x14001527e  mov     rcx, [rcx+58h]
0x140015282  call    WPP_SF_d
0x140015287  mov     eax, edi
0x140015289  jmp     short loc_1400152AF
0x14001528b  xor     eax, eax
0x14001528d  jmp     short loc_1400152AF
0x14001528f  mov     edi, eax
0x140015291  mov     rbx, [rsp+98h+arg_0]
0x140015299  mov     rcx, [rbx]; this
0x14001529c  test    rcx, rcx
0x14001529f  jz      short loc_1400152A6
0x1400152a1  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x1400152a6  mov     qword ptr [rbx], 0
0x1400152ad  mov     eax, edi
0x1400152af  lea     r11, [rsp+98h+var_28]
0x1400152b4  mov     rbx, [r11+38h]
0x1400152b8  mov     rsi, [r11+40h]
0x1400152bc  mov     rsp, r11
0x1400152bf  pop     r15
0x1400152c1  pop     r14
0x1400152c3  pop     r13
0x1400152c5  pop     r12
0x1400152c7  pop     rdi
0x1400152c8  retn
```
