# DiskModeSelect

- ea: `0x140015760`
- end: `0x1400159b4`
- name: `DiskModeSelect`
- size: `596`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, void *Src, size_t Size, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000e200`
- `0x14000f804`

## callees

- `0x140004078`
- `0x140005bf0`
- `0x140005d00`
- `0x140006000`
- `0x140015760`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140015977`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015977`
- `ntoskrnl!ExAllocatePool2` at `0x140015822`
- `ntoskrnl!ExAllocatePool2` at `0x140015822`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x140015941`
- `CLASSPNP!ClassSendSrbSynchronous` at `0x140015941`

## pseudocode

```c
__int64 __fastcall DiskModeSelect(PDEVICE_OBJECT DeviceObject, void *Src, size_t Size, char a4)
{
  _BYTE *DeviceExtension; // r14
  size_t v6; // rsi
  ULONG v10; // edi
  __int64 Pool2; // rax
  void *v12; // rbx
  int v13; // r12d
  _BYTE *v14; // rdx
  int v15; // eax
  struct _SCSI_REQUEST_BLOCK *v16; // r14
  int v17; // eax
  char v18; // al
  unsigned int v19; // esi
  _DWORD v21[24]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE Srb[184]; // [rsp+90h] [rbp-70h] BYREF

  DeviceExtension = DeviceObject->DeviceExtension;
  v6 = (unsigned int)Size;
  memset(v21, 0, 0x58u);
  memset(Srb, 0, sizeof(Srb));
  if ( *((_DWORD *)DeviceExtension + 143) )
  {
    v10 = v6 + 12;
    Pool2 = ExAllocatePool2(72, (unsigned int)(v6 + 12), 1296327507);
    v12 = (void *)Pool2;
    if ( Pool2 )
    {
      *(_BYTE *)(Pool2 + 3) = 8;
      *(_BYTE *)(Pool2 + 11) = DeviceExtension[574];
      *(_WORD *)(Pool2 + 9) = __PAIR16__(BYTE1(*((_DWORD *)DeviceExtension + 143)), DeviceExtension[572]);
      memmove((void *)(Pool2 + 12), Src, v6);
      v13 = 1;
      if ( *(_BYTE *)(*((_QWORD *)DeviceExtension + 66) + 30LL) == 1 )
      {
        Srb[2] = 40;
        strcpy(Srb, "\b");
        v14 = &Srb[168];
        *(_DWORD *)&Srb[8] = 1397899864;
        *(_WORD *)&Srb[36] = 2;
        *(_DWORD *)&Srb[12] = 1;
        *(_QWORD *)&Srb[16] = 184;
        *(_DWORD *)&Srb[52] = 128;
        *(_DWORD *)&Srb[56] = 1;
        v15 = *((_DWORD *)DeviceExtension + 146);
        v16 = (struct _SCSI_REQUEST_BLOCK *)Srb;
        *(_WORD *)&Srb[128] = 1;
        *(_DWORD *)&Srb[40] = 2 * v15;
        *(_DWORD *)&Srb[132] = 4;
        *(_DWORD *)&Srb[120] = 144;
        *(_DWORD *)&Srb[144] = 64;
        *(_DWORD *)&Srb[148] = 32;
        Srb[154] = 6;
      }
      else
      {
        BYTE2(v21[2]) = 6;
        v14 = &v21[18];
        v17 = *((_DWORD *)DeviceExtension + 146);
        v16 = (struct _SCSI_REQUEST_BLOCK *)v21;
        v21[5] = 2 * v17;
      }
      v18 = v14[1];
      *v14 = 21;
      v14[4] = v10;
      v14[1] = v18 ^ (a4 ^ v18) & 1 | 0x10;
      while ( 1 )
      {
        v19 = ClassSendSrbSynchronous(DeviceObject, v16, v12, v10, 1u);
        if ( v19 != -2147483626 )
          break;
        if ( !v13-- )
          goto LABEL_18;
      }
      if ( (v16->SrbStatus & 0x3F) == 0x12 )
        v19 = 0;
LABEL_18:
      ExFreePoolWithTag(v12, 0);
      return v19;
    }
    else
    {
      return 3221225626LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140015760  push    rbp
0x140015762  push    rsi
0x140015763  push    r12
0x140015765  push    r13
0x140015767  push    r14
0x140015769  push    r15
0x14001576b  lea     rbp, [rsp-68h]
0x140015770  sub     rsp, 168h
0x140015777  mov     rax, cs:__security_cookie
0x14001577e  xor     rax, rsp
0x140015781  mov     [rbp+90h+var_40], rax
0x140015785  mov     r14, [rcx+40h]
0x140015789  mov     r12, rdx
0x14001578c  mov     esi, r8d
0x14001578f  mov     r15, rcx
0x140015792  xor     edx, edx; Val
0x140015794  lea     rcx, [rsp+190h+var_160]; void *
0x140015799  mov     r8d, 58h ; 'X'; Size
0x14001579f  movzx   r13d, r9b
0x1400157a3  call    memset
0x1400157a8  xor     edx, edx; Val
0x1400157aa  lea     rcx, [rbp+90h+Srb]; void *
0x1400157ae  mov     r8d, 0B8h; Size
0x1400157b4  call    memset
0x1400157b9  cmp     dword ptr [r14+23Ch], 0
0x1400157c1  jnz     short loc_140015802
0x1400157c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400157ca  lea     rax, WPP_GLOBAL_Control
0x1400157d1  cmp     rcx, rax
0x1400157d4  jz      short loc_1400157F8
0x1400157d6  mov     eax, [rcx+2Ch]
0x1400157d9  test    al, 10h
0x1400157db  jz      short loc_1400157F8
0x1400157dd  cmp     byte ptr [rcx+29h], 2
0x1400157e1  jb      short loc_1400157F8
0x1400157e3  mov     rcx, [rcx+18h]
0x1400157e7  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x1400157ee  mov     edx, 26h ; '&'
0x1400157f3  call    WPP_SF_
0x1400157f8  mov     eax, 0C000000Dh
0x1400157fd  jmp     loc_140015995
0x140015802  mov     [rsp+190h+arg_18], rbx
0x14001580a  mov     ecx, 48h ; 'H'
0x14001580f  mov     [rsp+190h+var_30], rdi
0x140015817  mov     r8d, 4D446353h
0x14001581d  lea     edi, [rsi+0Ch]
0x140015820  mov     edx, edi
0x140015822  call    cs:__imp_ExAllocatePool2
0x140015829  nop     dword ptr [rax+rax+00h]
0x14001582e  mov     rbx, rax
0x140015831  test    rax, rax
0x140015834  jnz     short loc_140015840
0x140015836  mov     eax, 0C000009Ah
0x14001583b  jmp     loc_140015985
0x140015840  mov     byte ptr [rax+3], 8
0x140015844  lea     rcx, [rbx+0Ch]; void *
0x140015848  movzx   eax, byte ptr [r14+23Eh]
0x140015850  mov     r8, rsi; Size
0x140015853  mov     [rbx+0Bh], al
0x140015856  mov     rdx, r12; Src
0x140015859  mov     eax, [r14+23Ch]
0x140015860  shr     eax, 8
0x140015863  mov     [rbx+0Ah], al
0x140015866  movzx   eax, byte ptr [r14+23Ch]
0x14001586e  mov     [rbx+9], al
0x140015871  call    memmove
0x140015876  mov     rax, [r14+210h]
0x14001587d  mov     r12d, 1
0x140015883  cmp     [rax+1Eh], r12b
0x140015887  jnz     short loc_1400158F8
0x140015889  mov     eax, 8
0x14001588e  mov     [rbp+90h+Srb.Function], 28h ; '('
0x140015892  mov     [rbp+90h+Srb.Length], ax
0x140015896  lea     rdx, [rbp+90h+var_58]
0x14001589a  mov     eax, 2
0x14001589f  mov     dword ptr [rbp+90h+Srb.QueueTag], 53524258h
0x1400158a6  mov     word ptr [rbp+90h+Srb.SenseInfoBuffer+4], ax
0x1400158aa  mov     [rbp+90h+Srb.SrbFlags], r12d
0x1400158ae  mov     qword ptr [rbp+90h+Srb.DataTransferLength], 0B8h
0x1400158b6  mov     dword ptr [rbp+90h+Srb.OriginalRequest+4], 80h
0x1400158bd  mov     dword ptr [rbp+90h+Srb.SrbExtension], r12d
0x1400158c1  mov     eax, [r14+248h]
0x1400158c8  lea     r14, [rbp+90h+Srb]
0x1400158cc  add     eax, eax
0x1400158ce  mov     [rbp+90h+var_80], r12w
0x1400158d3  mov     dword ptr [rbp+90h+Srb.NextSrb], eax
0x1400158d6  mov     [rbp+90h+var_7C], 4
0x1400158dd  mov     [rbp+90h+var_88], 90h
0x1400158e4  mov     [rbp+90h+var_70], 40h ; '@'
0x1400158eb  mov     [rbp+90h+var_6C], 20h ; ' '
0x1400158f2  mov     [rbp+90h+var_66], 6
0x1400158f6  jmp     short loc_140015914
0x1400158f8  mov     [rsp+190h+var_156], 6
0x1400158fd  lea     rdx, [rsp+190h+var_118]
0x140015902  mov     eax, [r14+248h]
0x140015909  lea     r14, [rsp+190h+var_160]
0x14001590e  add     eax, eax
0x140015910  mov     [rsp+190h+var_14C], eax
0x140015914  movzx   eax, byte ptr [rdx+1]
0x140015918  movzx   ecx, al
0x14001591b  mov     byte ptr [rdx], 15h
0x14001591e  xor     cl, r13b
0x140015921  mov     [rdx+4], dil
0x140015925  and     cl, r12b
0x140015928  xor     cl, al
0x14001592a  or      cl, 10h
0x14001592d  mov     [rdx+1], cl
0x140015930  mov     r9d, edi; BufferLength
0x140015933  mov     [rsp+190h+WriteToDevice], 1; WriteToDevice
0x140015938  mov     r8, rbx; BufferAddress
0x14001593b  mov     rdx, r14; Srb
0x14001593e  mov     rcx, r15; DeviceObject
0x140015941  call    cs:__imp_ClassSendSrbSynchronous
0x140015948  nop     dword ptr [rax+rax+00h]
0x14001594d  mov     esi, eax
0x14001594f  cmp     eax, 80000016h
0x140015954  jnz     short loc_140015962
0x140015956  mov     ecx, r12d
0x140015959  dec     r12d
0x14001595c  test    ecx, ecx
0x14001595e  jnz     short loc_140015930
0x140015960  jmp     short loc_140015972
0x140015962  movzx   ecx, byte ptr [r14+3]
0x140015967  xor     eax, eax
0x140015969  and     cl, 3Fh
0x14001596c  cmp     cl, 12h
0x14001596f  cmovz   esi, eax
0x140015972  xor     edx, edx; Tag
0x140015974  mov     rcx, rbx; P
0x140015977  call    cs:__imp_ExFreePoolWithTag
0x14001597e  nop     dword ptr [rax+rax+00h]
0x140015983  mov     eax, esi
0x140015985  mov     rbx, [rsp+190h+arg_18]
0x14001598d  mov     rdi, [rsp+190h+var_30]
0x140015995  mov     rcx, [rbp+90h+var_40]
0x140015999  xor     rcx, rsp; StackCookie
0x14001599c  call    __security_check_cookie
0x1400159a1  add     rsp, 168h
0x1400159a8  pop     r15
0x1400159aa  pop     r14
0x1400159ac  pop     r13
0x1400159ae  pop     r12
0x1400159b0  pop     rsi
0x1400159b1  pop     rbp
0x1400159b2  retn
```
