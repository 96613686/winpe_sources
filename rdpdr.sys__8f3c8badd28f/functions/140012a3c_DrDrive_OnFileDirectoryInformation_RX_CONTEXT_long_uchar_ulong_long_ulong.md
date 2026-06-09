# DrDrive::OnFileDirectoryInformation(_RX_CONTEXT *,long,uchar *,ulong,long &,ulong &)

- ea: `0x140012a3c`
- end: `0x140012beb`
- name: `?OnFileDirectoryInformation@DrDrive@@IEAAJPEAU_RX_CONTEXT@@JPEAEKAEAJAEAK@Z`
- size: `431`
- prototype: `__int64 __fastcall(DrDrive *__hidden this, struct _RX_CONTEXT *, int, unsigned __int8 *, unsigned int, int *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400131e0`
- `0x1400152a0`

## callees

- `0x14000324c`
- `0x1400065c0`
- `0x140012a3c`

## pseudocode

```c
__int64 __fastcall DrDrive::OnFileDirectoryInformation(
        DrDrive *this,
        struct _RX_CONTEXT *a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        int *a6,
        unsigned int *a7)
{
  PDFS_NAME_CONTEXT DfsNameContext; // rdi
  unsigned int v10; // ecx
  __int64 result; // rax
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // edx

  if ( a3 < 0 )
  {
    *a6 = a3;
    goto LABEL_24;
  }
  if ( a5 >= 0x40 )
  {
    if ( *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) < 0x40u )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_17;
      v15 = 31;
    }
    else
    {
      DfsNameContext = a2->Create.NtCreateParameters.DfsNameContext;
      *((_QWORD *)DfsNameContext + 6) = *((_QWORD *)a4 + 6);
      *((_QWORD *)DfsNameContext + 4) = *((_QWORD *)a4 + 4);
      *((_QWORD *)DfsNameContext + 1) = *((_QWORD *)a4 + 1);
      *((_QWORD *)DfsNameContext + 5) = *((_QWORD *)a4 + 5);
      *((_DWORD *)DfsNameContext + 14) = *((_DWORD *)a4 + 14);
      *((_DWORD *)DfsNameContext + 1) = *((_DWORD *)a4 + 1);
      *((_DWORD *)DfsNameContext + 15) = *((_DWORD *)a4 + 15);
      *((_QWORD *)DfsNameContext + 2) = *((_QWORD *)a4 + 2);
      *((_QWORD *)DfsNameContext + 3) = *((_QWORD *)a4 + 3);
      *(_DWORD *)DfsNameContext = *(_DWORD *)a4;
      *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) -= 64;
      v10 = *((_DWORD *)DfsNameContext + 15);
      if ( *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) >= v10 )
      {
        if ( a5 == v10 + 64 )
        {
          memmove((char *)DfsNameContext + 64, a4 + 64, v10);
          *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) -= *((_DWORD *)DfsNameContext + 15);
          *a6 = a3;
          *a7 = a5;
          return 0;
        }
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_22;
        v13 = 29;
        goto LABEL_21;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_17;
      v15 = 30;
    }
    WPP_SF_(v14->AttachedDevice, v15, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
LABEL_17:
    *a6 = -2147483643;
LABEL_24:
    v16 = 0;
    goto LABEL_25;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    goto LABEL_22;
  v13 = 32;
LABEL_21:
  WPP_SF_(v12->AttachedDevice, v13, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
LABEL_22:
  v16 = -1073741434;
  *a6 = -1073741434;
LABEL_25:
  result = v16;
  *a7 = 0;
  return result;
}

```

## disassembly

```asm
0x140012a3c  push    rbx
0x140012a3e  push    rbp
0x140012a3f  push    rsi
0x140012a40  push    rdi
0x140012a41  sub     rsp, 28h
0x140012a45  mov     ebp, r8d
0x140012a48  mov     rbx, rdx
0x140012a4b  test    r8d, r8d
0x140012a4e  js      loc_140012BC8
0x140012a54  mov     esi, [rsp+48h+arg_20]
0x140012a58  cmp     esi, 40h ; '@'
0x140012a5b  jb      loc_140012B8C
0x140012a61  cmp     dword ptr [rdx+1D8h], 40h ; '@'
0x140012a68  jb      loc_140012B51
0x140012a6e  mov     rdi, [rdx+1C8h]
0x140012a75  mov     rax, [r9+30h]
0x140012a79  mov     [rdi+30h], rax
0x140012a7d  mov     rax, [r9+20h]
0x140012a81  mov     [rdi+20h], rax
0x140012a85  mov     rax, [r9+8]
0x140012a89  mov     [rdi+8], rax
0x140012a8d  mov     rax, [r9+28h]
0x140012a91  mov     [rdi+28h], rax
0x140012a95  mov     eax, [r9+38h]
0x140012a99  mov     [rdi+38h], eax
0x140012a9c  mov     eax, [r9+4]
0x140012aa0  mov     [rdi+4], eax
0x140012aa3  mov     eax, [r9+3Ch]
0x140012aa7  mov     [rdi+3Ch], eax
0x140012aaa  mov     rax, [r9+10h]
0x140012aae  mov     [rdi+10h], rax
0x140012ab2  mov     rax, [r9+18h]
0x140012ab6  mov     [rdi+18h], rax
0x140012aba  mov     eax, [r9]
0x140012abd  mov     [rdi], eax
0x140012abf  add     dword ptr [rdx+1D8h], 0FFFFFFC0h
0x140012ac6  mov     ecx, [rdi+3Ch]
0x140012ac9  cmp     [rdx+1D8h], ecx
0x140012acf  jb      short loc_140012B31
0x140012ad1  lea     eax, [rcx+40h]
0x140012ad4  cmp     esi, eax
0x140012ad6  jnz     short loc_140012B09
0x140012ad8  mov     r8d, ecx; Size
0x140012adb  lea     rdx, [r9+40h]; Src
0x140012adf  lea     rcx, [rdi+40h]; void *
0x140012ae3  call    memmove
0x140012ae8  mov     eax, [rdi+3Ch]
0x140012aeb  sub     [rbx+1D8h], eax
0x140012af1  mov     rax, [rsp+48h+arg_28]
0x140012af6  mov     [rax], ebp
0x140012af8  mov     rax, [rsp+48h+arg_30]
0x140012b00  mov     [rax], esi
0x140012b02  xor     eax, eax
0x140012b04  jmp     loc_140012BE1
0x140012b09  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b10  lea     rax, WPP_GLOBAL_Control
0x140012b17  cmp     rcx, rax
0x140012b1a  jz      loc_140012BBA
0x140012b20  cmp     byte ptr [rcx+29h], 2
0x140012b24  jb      loc_140012BBA
0x140012b2a  mov     edx, 1Dh
0x140012b2f  jmp     short loc_140012BAA
0x140012b31  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b38  lea     rax, WPP_GLOBAL_Control
0x140012b3f  cmp     rcx, rax
0x140012b42  jz      short loc_140012B7F
0x140012b44  cmp     byte ptr [rcx+29h], 2
0x140012b48  jb      short loc_140012B7F
0x140012b4a  mov     edx, 1Eh
0x140012b4f  jmp     short loc_140012B6F
0x140012b51  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b58  lea     rax, WPP_GLOBAL_Control
0x140012b5f  cmp     rcx, rax
0x140012b62  jz      short loc_140012B7F
0x140012b64  cmp     byte ptr [rcx+29h], 2
0x140012b68  jb      short loc_140012B7F
0x140012b6a  mov     edx, 1Fh
0x140012b6f  mov     rcx, [rcx+18h]
0x140012b73  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140012b7a  call    WPP_SF_
0x140012b7f  mov     rax, [rsp+48h+arg_28]
0x140012b84  mov     dword ptr [rax], 80000005h
0x140012b8a  jmp     short loc_140012BCF
0x140012b8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b93  lea     rax, WPP_GLOBAL_Control
0x140012b9a  cmp     rcx, rax
0x140012b9d  jz      short loc_140012BBA
0x140012b9f  cmp     byte ptr [rcx+29h], 2
0x140012ba3  jb      short loc_140012BBA
0x140012ba5  mov     edx, 20h ; ' '
0x140012baa  mov     rcx, [rcx+18h]
0x140012bae  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140012bb5  call    WPP_SF_
0x140012bba  mov     rax, [rsp+48h+arg_28]
0x140012bbf  mov     edx, 0C0000186h
0x140012bc4  mov     [rax], edx
0x140012bc6  jmp     short loc_140012BD1
0x140012bc8  mov     rax, [rsp+48h+arg_28]
0x140012bcd  mov     [rax], ebp
0x140012bcf  xor     edx, edx
0x140012bd1  mov     rcx, [rsp+48h+arg_30]
0x140012bd9  mov     eax, edx
0x140012bdb  mov     dword ptr [rcx], 0
0x140012be1  add     rsp, 28h
0x140012be5  pop     rdi
0x140012be6  pop     rsi
0x140012be7  pop     rbp
0x140012be8  pop     rbx
0x140012be9  retn
```
