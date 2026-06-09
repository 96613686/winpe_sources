# DrDrive::OnFileFullDirectoryInformation(_RX_CONTEXT *,long,uchar *,ulong,long &,ulong &)

- ea: `0x140012bf4`
- end: `0x140012daa`
- name: `?OnFileFullDirectoryInformation@DrDrive@@IEAAJPEAU_RX_CONTEXT@@JPEAEKAEAJAEAK@Z`
- size: `438`
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
- `0x140012bf4`

## pseudocode

```c
__int64 __fastcall DrDrive::OnFileFullDirectoryInformation(
        DrDrive *this,
        struct _RX_CONTEXT *a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        int *a6,
        unsigned int *a7)
{
  PDFS_NAME_CONTEXT DfsNameContext; // rbx
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
  if ( a5 >= 0x44 )
  {
    if ( *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) < 0x44u )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_17;
      v15 = 35;
    }
    else
    {
      DfsNameContext = a2->Create.NtCreateParameters.DfsNameContext;
      *((_QWORD *)DfsNameContext + 6) = *((_QWORD *)a4 + 6);
      *((_QWORD *)DfsNameContext + 4) = *((_QWORD *)a4 + 4);
      *((_QWORD *)DfsNameContext + 1) = *((_QWORD *)a4 + 1);
      *((_DWORD *)DfsNameContext + 16) = *((_DWORD *)a4 + 16);
      *((_QWORD *)DfsNameContext + 5) = *((_QWORD *)a4 + 5);
      *((_DWORD *)DfsNameContext + 14) = *((_DWORD *)a4 + 14);
      *((_DWORD *)DfsNameContext + 1) = *((_DWORD *)a4 + 1);
      *((_DWORD *)DfsNameContext + 15) = *((_DWORD *)a4 + 15);
      *((_QWORD *)DfsNameContext + 2) = *((_QWORD *)a4 + 2);
      *((_QWORD *)DfsNameContext + 3) = *((_QWORD *)a4 + 3);
      *(_DWORD *)DfsNameContext = *(_DWORD *)a4;
      *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) -= 68;
      v10 = *((_DWORD *)DfsNameContext + 15);
      if ( *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) >= v10 )
      {
        if ( a5 == v10 + 68 )
        {
          memmove((char *)DfsNameContext + 68, a4 + 68, v10);
          *((_DWORD *)&a2->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) -= *((_DWORD *)DfsNameContext + 15);
          *a6 = a3;
          *a7 = a5;
          return 0;
        }
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_22;
        v13 = 33;
        goto LABEL_21;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_17;
      v15 = 34;
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
  v13 = 36;
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
0x140012bf4  push    rbx
0x140012bf6  push    rbp
0x140012bf7  push    rsi
0x140012bf8  push    rdi
0x140012bf9  sub     rsp, 28h
0x140012bfd  mov     ebp, r8d
0x140012c00  mov     rdi, rdx
0x140012c03  test    r8d, r8d
0x140012c06  js      loc_140012D87
0x140012c0c  mov     esi, [rsp+48h+arg_20]
0x140012c10  cmp     esi, 44h ; 'D'
0x140012c13  jb      loc_140012D4B
0x140012c19  cmp     dword ptr [rdx+1D8h], 44h ; 'D'
0x140012c20  jb      loc_140012D10
0x140012c26  mov     rbx, [rdx+1C8h]
0x140012c2d  mov     rax, [r9+30h]
0x140012c31  mov     [rbx+30h], rax
0x140012c35  mov     rax, [r9+20h]
0x140012c39  mov     [rbx+20h], rax
0x140012c3d  mov     rax, [r9+8]
0x140012c41  mov     [rbx+8], rax
0x140012c45  mov     eax, [r9+40h]
0x140012c49  mov     [rbx+40h], eax
0x140012c4c  mov     rax, [r9+28h]
0x140012c50  mov     [rbx+28h], rax
0x140012c54  mov     eax, [r9+38h]
0x140012c58  mov     [rbx+38h], eax
0x140012c5b  mov     eax, [r9+4]
0x140012c5f  mov     [rbx+4], eax
0x140012c62  mov     eax, [r9+3Ch]
0x140012c66  mov     [rbx+3Ch], eax
0x140012c69  mov     rax, [r9+10h]
0x140012c6d  mov     [rbx+10h], rax
0x140012c71  mov     rax, [r9+18h]
0x140012c75  mov     [rbx+18h], rax
0x140012c79  mov     eax, [r9]
0x140012c7c  mov     [rbx], eax
0x140012c7e  add     dword ptr [rdx+1D8h], 0FFFFFFBCh
0x140012c85  mov     ecx, [rbx+3Ch]
0x140012c88  cmp     [rdx+1D8h], ecx
0x140012c8e  jb      short loc_140012CF0
0x140012c90  lea     eax, [rcx+44h]
0x140012c93  cmp     esi, eax
0x140012c95  jnz     short loc_140012CC8
0x140012c97  mov     r8d, ecx; Size
0x140012c9a  lea     rdx, [r9+44h]; Src
0x140012c9e  lea     rcx, [rbx+44h]; void *
0x140012ca2  call    memmove
0x140012ca7  mov     eax, [rbx+3Ch]
0x140012caa  sub     [rdi+1D8h], eax
0x140012cb0  mov     rax, [rsp+48h+arg_28]
0x140012cb5  mov     [rax], ebp
0x140012cb7  mov     rax, [rsp+48h+arg_30]
0x140012cbf  mov     [rax], esi
0x140012cc1  xor     eax, eax
0x140012cc3  jmp     loc_140012DA0
0x140012cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140012ccf  lea     rax, WPP_GLOBAL_Control
0x140012cd6  cmp     rcx, rax
0x140012cd9  jz      loc_140012D79
0x140012cdf  cmp     byte ptr [rcx+29h], 2
0x140012ce3  jb      loc_140012D79
0x140012ce9  mov     edx, 21h ; '!'
0x140012cee  jmp     short loc_140012D69
0x140012cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x140012cf7  lea     rax, WPP_GLOBAL_Control
0x140012cfe  cmp     rcx, rax
0x140012d01  jz      short loc_140012D3E
0x140012d03  cmp     byte ptr [rcx+29h], 2
0x140012d07  jb      short loc_140012D3E
0x140012d09  mov     edx, 22h ; '"'
0x140012d0e  jmp     short loc_140012D2E
0x140012d10  mov     rcx, cs:WPP_GLOBAL_Control
0x140012d17  lea     rax, WPP_GLOBAL_Control
0x140012d1e  cmp     rcx, rax
0x140012d21  jz      short loc_140012D3E
0x140012d23  cmp     byte ptr [rcx+29h], 2
0x140012d27  jb      short loc_140012D3E
0x140012d29  mov     edx, 23h ; '#'
0x140012d2e  mov     rcx, [rcx+18h]
0x140012d32  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140012d39  call    WPP_SF_
0x140012d3e  mov     rax, [rsp+48h+arg_28]
0x140012d43  mov     dword ptr [rax], 80000005h
0x140012d49  jmp     short loc_140012D8E
0x140012d4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140012d52  lea     rax, WPP_GLOBAL_Control
0x140012d59  cmp     rcx, rax
0x140012d5c  jz      short loc_140012D79
0x140012d5e  cmp     byte ptr [rcx+29h], 2
0x140012d62  jb      short loc_140012D79
0x140012d64  mov     edx, 24h ; '$'
0x140012d69  mov     rcx, [rcx+18h]
0x140012d6d  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140012d74  call    WPP_SF_
0x140012d79  mov     rax, [rsp+48h+arg_28]
0x140012d7e  mov     edx, 0C0000186h
0x140012d83  mov     [rax], edx
0x140012d85  jmp     short loc_140012D90
0x140012d87  mov     rax, [rsp+48h+arg_28]
0x140012d8c  mov     [rax], ebp
0x140012d8e  xor     edx, edx
0x140012d90  mov     rcx, [rsp+48h+arg_30]
0x140012d98  mov     eax, edx
0x140012d9a  mov     dword ptr [rcx], 0
0x140012da0  add     rsp, 28h
0x140012da4  pop     rdi
0x140012da5  pop     rsi
0x140012da6  pop     rbp
0x140012da7  pop     rbx
0x140012da8  retn
```
