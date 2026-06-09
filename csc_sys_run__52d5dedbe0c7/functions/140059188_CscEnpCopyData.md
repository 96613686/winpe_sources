# CscEnpCopyData

- ea: `0x140059188`
- end: `0x1400593d3`
- name: `CscEnpCopyData`
- size: `587`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1400593dc`

## callees

- `0x14000be90`
- `0x14000d960`
- `0x140010f6c`
- `0x140018fd0`
- `0x14001b710`
- `0x140029a78`
- `0x140029e9c`
- `0x140059188`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400592c5`
- `ntoskrnl!ExAllocatePool2` at `0x1400592c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005935d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005935d`

## pseudocode

```c
__int64 __fastcall CscEnpCopyData(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v5; // r14
  int File; // ebx
  int v11; // edi
  __int64 v12; // r9
  struct _FILE_OBJECT *Pool2; // rsi
  ULONG v15; // [rsp+30h] [rbp-20h] BYREF
  int v16; // [rsp+34h] [rbp-1Ch] BYREF
  void *v17; // [rsp+38h] [rbp-18h] BYREF
  void *v18; // [rsp+40h] [rbp-10h] BYREF
  __int64 v19; // [rsp+48h] [rbp-8h] BYREF

  v5 = 0;
  v18 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v19 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids, a2, a4, a5);
  v19 = a5;
  File = CscStorepLowIoOpenFileByFileIdPoster((__int64)&v18, a1, a2, 2032127, 7, 32);
  if ( File >= 0 )
  {
    File = CscStorepLowIoOpenFileByFileIdPoster((__int64)&v17, a3, a4, 2032127, 7, 32);
    if ( File >= 0 )
    {
      File = CscStorepLowIoSetInformationFilePoster((__int64)v17, (__int64)&v19, 8u, 0x14u);
      if ( File >= 0 )
      {
        if ( a5 )
        {
          Pool2 = (struct _FILE_OBJECT *)ExAllocatePool2(66, 4096, 557871939, v12);
          while ( 1 )
          {
            File = CscStorepLowIoReadFileEx(v18, v5, 0x1000u, Pool2, 1, (__int64)&v15);
            if ( ((File + 0x80000000) & 0x80000000) == 0 && File != -1073741807 )
            {
              v11 = 371;
              goto LABEL_21;
            }
            if ( !v15 )
              break;
            File = CscStorepLowIoWriteFileEx(v17, v5, v15, Pool2, 1, (__int64)&v16);
            if ( File < 0 )
            {
              v11 = 386;
              goto LABEL_21;
            }
            v5 += v15;
          }
          v11 = 0;
          File = 0;
LABEL_21:
          if ( Pool2 )
            ExFreePoolWithTag(Pool2, 0x21407343u);
        }
        else
        {
          File = 0;
          v11 = 354;
        }
      }
      else
      {
        v11 = 349;
      }
    }
    else
    {
      v11 = 343;
    }
  }
  else
  {
    v11 = 335;
  }
  if ( v17 )
    CscStorepLowIoClosePoster(v17);
  if ( v18 )
    CscStorepLowIoClosePoster(v18);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids, v5, File, v11);
  return (unsigned int)File;
}

```

## disassembly

```asm
0x140059188  push    rbp
0x14005918a  push    rbx
0x14005918b  push    rsi
0x14005918c  push    rdi
0x14005918d  push    r12
0x14005918f  push    r14
0x140059191  push    r15
0x140059193  mov     rbp, rsp
0x140059196  sub     rsp, 50h
0x14005919a  xor     r14d, r14d
0x14005919d  mov     [rbp+var_10], 0
0x1400591a5  mov     [rbp+var_20], r14d
0x1400591a9  mov     rsi, r9
0x1400591ac  mov     [rbp+var_1C], r14d
0x1400591b0  mov     r12, r8
0x1400591b3  mov     rbx, rdx
0x1400591b6  mov     [rbp+var_18], 0
0x1400591be  mov     r15, rcx
0x1400591c1  mov     [rbp+var_8], 0
0x1400591c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400591d0  lea     rax, WPP_GLOBAL_Control
0x1400591d7  mov     rdi, [rbp+arg_20]
0x1400591db  cmp     rcx, rax
0x1400591de  jz      short loc_14005920A
0x1400591e0  test    dword ptr [rcx+2Ch], 40000h
0x1400591e7  jz      short loc_14005920A
0x1400591e9  mov     rcx, [rcx+18h]
0x1400591ed  lea     edx, [r14+0Dh]
0x1400591f1  mov     [rsp+50h+var_28], rdi
0x1400591f6  lea     r8, WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids
0x1400591fd  mov     [rsp+50h+var_30], r9
0x140059202  mov     r9, rbx
0x140059205  call    WPP_SF_qqq
0x14005920a  mov     dword ptr [rsp+50h+var_28], 20h ; ' '
0x140059212  lea     rcx, [rbp+var_10]
0x140059216  mov     r9d, 1F01FFh
0x14005921c  mov     dword ptr [rsp+50h+var_30], 7
0x140059224  mov     r8, rbx
0x140059227  mov     [rbp+var_8], rdi
0x14005922b  mov     rdx, r15
0x14005922e  call    CscStorepLowIoOpenFileByFileIdPoster
0x140059233  mov     ebx, eax
0x140059235  test    eax, eax
0x140059237  jns     short loc_140059243
0x140059239  mov     edi, 14Fh
0x14005923e  jmp     loc_140059369
0x140059243  mov     dword ptr [rsp+50h+var_28], 20h ; ' '
0x14005924b  lea     rcx, [rbp+var_18]
0x14005924f  mov     r9d, 1F01FFh
0x140059255  mov     dword ptr [rsp+50h+var_30], 7
0x14005925d  mov     r8, rsi
0x140059260  mov     rdx, r12
0x140059263  call    CscStorepLowIoOpenFileByFileIdPoster
0x140059268  mov     ebx, eax
0x14005926a  test    eax, eax
0x14005926c  jns     short loc_140059278
0x14005926e  mov     edi, 157h
0x140059273  jmp     loc_140059369
0x140059278  mov     rcx, [rbp+var_18]
0x14005927c  lea     rdx, [rbp+var_8]
0x140059280  mov     r9d, 14h
0x140059286  lea     r8d, [r9-0Ch]
0x14005928a  call    CscStorepLowIoSetInformationFilePoster
0x14005928f  mov     ebx, eax
0x140059291  test    eax, eax
0x140059293  jns     short loc_14005929F
0x140059295  mov     edi, 15Dh
0x14005929a  jmp     loc_140059369
0x14005929f  test    rdi, rdi
0x1400592a2  jnz     short loc_1400592B0
0x1400592a4  xor     ebx, ebx
0x1400592a6  mov     edi, 162h
0x1400592ab  jmp     loc_140059369
0x1400592b0  mov     r15d, 21407343h
0x1400592b6  mov     edi, 1000h
0x1400592bb  mov     r8d, r15d
0x1400592be  mov     edx, edi
0x1400592c0  mov     ecx, 42h ; 'B'
0x1400592c5  call    cs:__imp_ExAllocatePool2
0x1400592cc  nop     dword ptr [rax+rax+00h]
0x1400592d1  mov     rsi, rax
0x1400592d4  mov     r12d, 80000000h
0x1400592da  mov     rcx, [rbp+var_10]
0x1400592de  lea     rax, [rbp+var_20]
0x1400592e2  mov     [rsp+50h+var_28], rax
0x1400592e7  mov     r9, rsi
0x1400592ea  mov     r8d, edi
0x1400592ed  mov     byte ptr [rsp+50h+var_30], 1
0x1400592f2  mov     rdx, r14
0x1400592f5  call    CscStorepLowIoReadFileEx
0x1400592fa  mov     ebx, eax
0x1400592fc  add     eax, r12d
0x1400592ff  test    r12d, eax
0x140059302  jnz     short loc_14005930C
0x140059304  cmp     ebx, 0C0000011h
0x14005930a  jnz     short loc_140059340
0x14005930c  mov     r8d, [rbp+var_20]
0x140059310  test    r8d, r8d
0x140059313  jz      short loc_14005934E
0x140059315  mov     rcx, [rbp+var_18]
0x140059319  lea     rax, [rbp+var_1C]
0x14005931d  mov     [rsp+50h+var_28], rax
0x140059322  mov     r9, rsi
0x140059325  mov     rdx, r14
0x140059328  mov     byte ptr [rsp+50h+var_30], 1
0x14005932d  call    CscStorepLowIoWriteFileEx
0x140059332  mov     ebx, eax
0x140059334  test    eax, eax
0x140059336  js      short loc_140059347
0x140059338  mov     eax, [rbp+var_20]
0x14005933b  add     r14, rax
0x14005933e  jmp     short loc_1400592DA
0x140059340  mov     edi, 173h
0x140059345  jmp     short loc_140059352
0x140059347  mov     edi, 182h
0x14005934c  jmp     short loc_140059352
0x14005934e  xor     edi, edi
0x140059350  xor     ebx, ebx
0x140059352  test    rsi, rsi
0x140059355  jz      short loc_140059369
0x140059357  mov     edx, r15d; Tag
0x14005935a  mov     rcx, rsi; P
0x14005935d  call    cs:__imp_ExFreePoolWithTag
0x140059364  nop     dword ptr [rax+rax+00h]
0x140059369  mov     rcx, [rbp+var_18]
0x14005936d  test    rcx, rcx
0x140059370  jz      short loc_140059377
0x140059372  call    CscStorepLowIoClosePoster
0x140059377  mov     rcx, [rbp+var_10]
0x14005937b  test    rcx, rcx
0x14005937e  jz      short loc_140059385
0x140059380  call    CscStorepLowIoClosePoster
0x140059385  mov     rcx, cs:WPP_GLOBAL_Control
0x14005938c  lea     rax, WPP_GLOBAL_Control
0x140059393  cmp     rcx, rax
0x140059396  jz      short loc_1400593C1
0x140059398  test    dword ptr [rcx+2Ch], 40000h
0x14005939f  jz      short loc_1400593C1
0x1400593a1  mov     rcx, [rcx+18h]
0x1400593a5  lea     r8, WPP_20a5a69782de398b2c5441ddc3dd82b5_Traceguids
0x1400593ac  mov     edx, 0Eh
0x1400593b1  mov     dword ptr [rsp+50h+var_28], edi
0x1400593b5  mov     r9, r14
0x1400593b8  mov     dword ptr [rsp+50h+var_30], ebx
0x1400593bc  call    WPP_SF_qDD
0x1400593c1  mov     eax, ebx
0x1400593c3  add     rsp, 50h
0x1400593c7  pop     r15
0x1400593c9  pop     r14
0x1400593cb  pop     r12
0x1400593cd  pop     rdi
0x1400593ce  pop     rsi
0x1400593cf  pop     rbx
0x1400593d0  pop     rbp
0x1400593d1  retn
```
