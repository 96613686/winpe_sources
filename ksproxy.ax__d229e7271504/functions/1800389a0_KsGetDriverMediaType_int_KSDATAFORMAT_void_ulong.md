# KsGetDriverMediaType(int,KSDATAFORMAT * *,void *,ulong)

- ea: `0x1800389a0`
- end: `0x180038c71`
- name: `?KsGetDriverMediaType@@YAJHPEAPEATKSDATAFORMAT@@PEAXK@Z`
- size: `721`
- prototype: `__int64 __fastcall(int, union KSDATAFORMAT **, char *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x18002dd70`

## callees

- `0x1800063a0`
- `0x18000bde0`
- `0x18001f1c4`
- `0x18001f210`
- `0x180025860`
- `0x1800389a0`
- `0x180044850`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180038c4a`
- `ole32!CoTaskMemFree` at `0x180038c4a`

## pseudocode

```c
__int64 __fastcall KsGetDriverMediaType(int a1, union KSDATAFORMAT **a2, char *a3, int a4)
{
  unsigned int v6; // edi
  __int64 result; // rax
  _DWORD *v8; // r15
  unsigned int v9; // ecx
  unsigned int *v10; // rbx
  DWORD v11; // esi
  _DWORD *v12; // r14
  GUID *v13; // rax
  GUID *v14; // rdi
  signed int v15; // ebx
  GUID *v16; // r13
  int v17; // eax
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  DWORD v20; // eax
  unsigned __int64 v21; // rdx
  union KSDATAFORMAT *v22; // r14
  LPVOID pv[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+90h] [rbp+40h] BYREF
  union KSDATAFORMAT **v25; // [rsp+98h] [rbp+48h]

  v25 = a2;
  pv[0] = 0;
  v6 = a1;
  if ( a1 < 0 )
    return 2147942487LL;
  if ( (int)KsGetMultiplePinFactoryItems(a3, a4, 13, pv) >= 0
    || (result = KsGetMultiplePinFactoryItems(a3, a4, 3, pv), (int)result >= 0) )
  {
    v8 = pv[0];
    if ( !pv[0] )
      return 2147549183LL;
    v9 = *((_DWORD *)pv[0] + 1);
    if ( v6 >= v9 )
    {
LABEL_37:
      v15 = 262403;
      goto LABEL_38;
    }
    NumberOfBytesTransferred = 0;
    v10 = (unsigned int *)((char *)pv[0] + 8);
    while ( v6 )
    {
      if ( (v10[1] & 2) != 0 )
      {
        v8[1] = --v9;
        if ( v6 >= v9 )
          goto LABEL_37;
        v10 = (unsigned int *)((char *)v10 + ((*v10 + 7) & 0xFFFFFFF8));
      }
      v10 = (unsigned int *)((char *)v10 + ((*v10 + 7) & 0xFFFFFFF8));
      v8[1] = --v9;
      --v6;
    }
    v11 = *v10 + 40;
    if ( (v10[1] & 2) != 0 )
    {
      v12 = (unsigned int *)((char *)v10 + ((*v10 + 7) & 0xFFFFFFF8));
      v11 = *v12 + ((*v10 + 47) & 0xFFFFFFF8);
    }
    else
    {
      v12 = 0;
    }
    v13 = (GUID *)operator new[](v11);
    v14 = v13;
    if ( !v13 )
      goto LABEL_18;
    *(_DWORD *)v13[1].Data4 = a4;
    *(_DWORD *)&v13[1].Data2 = 1;
    v16 = v13 + 2;
    *v13 = GUID_8c134960_51ad_11cf_878a_94f801c10000;
    v13[1].Data1 = 4;
    *(_DWORD *)&v13[1].Data4[4] = 0;
    v17 = *v10;
    *(_DWORD *)&v16->Data2 = 1;
    v16->Data1 = v17 + 8;
    memcpy_0(v16->Data4, v10, *v10);
    if ( v12 )
    {
      v18 = *v12 + ((v16->Data1 + 7) & 0xFFFFFFF8);
      ++*(_DWORD *)&v16->Data2;
      v16->Data1 = v18;
      memcpy_0((char *)v16 + v18 - (unsigned int)*v12, v12, (unsigned int)*v12);
    }
    v15 = KsSynchronousDeviceControl(a3, 0x2F0003u, v14, v11, 0, 0, &NumberOfBytesTransferred);
    if ( v15 != -2147024774 )
      goto LABEL_27;
    LODWORD(pv[0]) = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids);
    v15 = KsSynchronousDeviceControl(a3, 0x2F0003u, v14, v11, pv, 4u, &NumberOfBytesTransferred);
    if ( v15 >= 0 )
    {
      v20 = (DWORD)pv[0];
      NumberOfBytesTransferred = (DWORD)pv[0];
    }
    else
    {
LABEL_27:
      if ( v15 != -2147024662 )
        goto LABEL_36;
      v20 = NumberOfBytesTransferred;
    }
    if ( v20 < 0x40 )
    {
      v15 = -2147418113;
    }
    else
    {
      v22 = (union KSDATAFORMAT *)operator new[](v20);
      if ( !v22 )
      {
        operator delete(v14, v21);
LABEL_18:
        v15 = -2147024882;
LABEL_38:
        CoTaskMemFree(v8);
        return (unsigned int)v15;
      }
      v15 = KsSynchronousDeviceControl(
              a3,
              0x2F0003u,
              v14,
              v11,
              v22,
              NumberOfBytesTransferred,
              &NumberOfBytesTransferred);
      if ( v15 < 0 )
        operator delete(v22, v19);
      else
        *v25 = v22;
    }
LABEL_36:
    operator delete(v14, v19);
    goto LABEL_38;
  }
  return result;
}

```

## disassembly

```asm
0x1800389a0  mov     [rsp-38h+arg_10], rbx
0x1800389a5  mov     [rsp-38h+arg_8], rdx
0x1800389aa  push    rbp
0x1800389ab  push    rsi
0x1800389ac  push    rdi
0x1800389ad  push    r12
0x1800389af  push    r13
0x1800389b1  push    r14
0x1800389b3  push    r15
0x1800389b5  mov     rbp, rsp
0x1800389b8  sub     rsp, 50h
0x1800389bc  mov     [rbp+pv], 0
0x1800389c4  mov     r13d, r9d
0x1800389c7  mov     r12, r8
0x1800389ca  mov     edi, ecx
0x1800389cc  test    ecx, ecx
0x1800389ce  jns     short loc_1800389DA
0x1800389d0  mov     eax, 80070057h
0x1800389d5  jmp     loc_180038C58
0x1800389da  lea     r9, [rbp+pv]
0x1800389de  mov     r8d, 0Dh
0x1800389e4  mov     edx, r13d
0x1800389e7  mov     rcx, r12; hFile
0x1800389ea  call    KsGetMultiplePinFactoryItems
0x1800389ef  test    eax, eax
0x1800389f1  jns     short loc_180038A10
0x1800389f3  lea     r9, [rbp+pv]
0x1800389f7  mov     r8d, 3
0x1800389fd  mov     edx, r13d
0x180038a00  mov     rcx, r12; hFile
0x180038a03  call    KsGetMultiplePinFactoryItems
0x180038a08  test    eax, eax
0x180038a0a  js      loc_180038C58
0x180038a10  mov     r15, [rbp+pv]
0x180038a14  test    r15, r15
0x180038a17  jnz     short loc_180038A23
0x180038a19  mov     eax, 8000FFFFh
0x180038a1e  jmp     loc_180038C58
0x180038a23  mov     ecx, [r15+4]
0x180038a27  cmp     edi, ecx
0x180038a29  jnb     loc_180038C42
0x180038a2f  mov     [rbp+NumberOfBytesTransferred], 0
0x180038a36  lea     rbx, [r15+8]
0x180038a3a  mov     edx, 0FFFFFFF8h
0x180038a3f  test    edi, edi
0x180038a41  jz      short loc_180038A77
0x180038a43  test    byte ptr [rbx+4], 2
0x180038a47  jz      short loc_180038A62
0x180038a49  dec     ecx
0x180038a4b  mov     [r15+4], ecx
0x180038a4f  cmp     edi, ecx
0x180038a51  jnb     loc_180038C42
0x180038a57  mov     eax, [rbx]
0x180038a59  add     eax, 7
0x180038a5c  and     rax, rdx
0x180038a5f  add     rbx, rax
0x180038a62  mov     eax, [rbx]
0x180038a64  add     eax, 7
0x180038a67  and     rax, rdx
0x180038a6a  add     rbx, rax
0x180038a6d  dec     ecx
0x180038a6f  mov     [r15+4], ecx
0x180038a73  dec     edi
0x180038a75  jmp     short loc_180038A3F
0x180038a77  test    byte ptr [rbx+4], 2
0x180038a7b  mov     eax, [rbx]
0x180038a7d  lea     esi, [rax+28h]
0x180038a80  jz      short loc_180038A96
0x180038a82  add     esi, 7
0x180038a85  lea     r14d, [rax+7]
0x180038a89  and     r14, rdx
0x180038a8c  and     esi, edx
0x180038a8e  add     r14, rbx
0x180038a91  add     esi, [r14]
0x180038a94  jmp     short loc_180038A99
0x180038a96  xor     r14d, r14d
0x180038a99  mov     ecx, esi; unsigned __int64
0x180038a9b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180038aa0  mov     rdi, rax
0x180038aa3  test    rax, rax
0x180038aa6  jnz     short loc_180038AB2
0x180038aa8  mov     ebx, 8007000Eh
0x180038aad  jmp     loc_180038C47
0x180038ab2  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x180038ab9  mov     [rax+18h], r13d
0x180038abd  mov     ecx, 1
0x180038ac2  mov     [rax+14h], ecx
0x180038ac5  lea     r13, [rax+20h]
0x180038ac9  movdqu  xmmword ptr [rax], xmm0
0x180038acd  mov     dword ptr [rax+10h], 4
0x180038ad4  mov     rdx, rbx; Src
0x180038ad7  mov     dword ptr [rax+1Ch], 0
0x180038ade  mov     eax, [rbx]
0x180038ae0  mov     [r13+4], ecx
0x180038ae4  add     eax, 8
0x180038ae7  mov     [r13+0], eax
0x180038aeb  lea     rcx, [r13+8]; void *
0x180038aef  mov     r8d, [rbx]; Size
0x180038af2  call    memcpy_0
0x180038af7  test    r14, r14
0x180038afa  jz      short loc_180038B26
0x180038afc  mov     ecx, [r13+0]
0x180038b00  mov     eax, 0FFFFFFF8h
0x180038b05  add     ecx, 7
0x180038b08  mov     rdx, r14; Src
0x180038b0b  and     ecx, eax
0x180038b0d  add     ecx, [r14]
0x180038b10  inc     dword ptr [r13+4]
0x180038b14  mov     [r13+0], ecx
0x180038b18  mov     r8d, [r14]; Size
0x180038b1b  sub     rcx, r8
0x180038b1e  add     rcx, r13; void *
0x180038b21  call    memcpy_0
0x180038b26  lea     rax, [rbp+NumberOfBytesTransferred]
0x180038b2a  xor     r13d, r13d
0x180038b2d  mov     [rsp+50h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180038b32  mov     r14d, 2F0003h
0x180038b38  mov     [rsp+50h+var_28], r13d; DWORD
0x180038b3d  mov     r9d, esi; nInBufferSize
0x180038b40  mov     r8, rdi; lpInBuffer
0x180038b43  mov     [rsp+50h+var_30], r13; LPVOID
0x180038b48  mov     edx, r14d; dwIoControlCode
0x180038b4b  mov     rcx, r12; hFile
0x180038b4e  call    KsSynchronousDeviceControl
0x180038b53  mov     ebx, eax
0x180038b55  cmp     eax, 8007007Ah
0x180038b5a  jnz     short loc_180038BC6
0x180038b5c  mov     dword ptr [rbp+pv], r13d
0x180038b60  mov     rcx, cs:WPP_GLOBAL_Control
0x180038b67  lea     rax, WPP_GLOBAL_Control
0x180038b6e  cmp     rcx, rax
0x180038b71  jz      short loc_180038B8D
0x180038b73  cmp     byte ptr [rcx+19h], 2
0x180038b77  jb      short loc_180038B8D
0x180038b79  mov     rcx, [rcx+10h]
0x180038b7d  lea     edx, [r13+18h]
0x180038b81  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x180038b88  call    WPP_SF_
0x180038b8d  lea     rax, [rbp+NumberOfBytesTransferred]
0x180038b91  mov     r9d, esi; nInBufferSize
0x180038b94  mov     [rsp+50h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180038b99  mov     r8, rdi; lpInBuffer
0x180038b9c  lea     rax, [rbp+pv]
0x180038ba0  mov     [rsp+50h+var_28], 4; DWORD
0x180038ba8  mov     edx, r14d; dwIoControlCode
0x180038bab  mov     [rsp+50h+var_30], rax; LPVOID
0x180038bb0  mov     rcx, r12; hFile
0x180038bb3  call    KsSynchronousDeviceControl
0x180038bb8  mov     ebx, eax
0x180038bba  test    eax, eax
0x180038bbc  js      short loc_180038BC6
0x180038bbe  mov     eax, dword ptr [rbp+pv]
0x180038bc1  mov     [rbp+NumberOfBytesTransferred], eax
0x180038bc4  jmp     short loc_180038BD1
0x180038bc6  cmp     ebx, 800700EAh
0x180038bcc  jnz     short loc_180038C38
0x180038bce  mov     eax, [rbp+NumberOfBytesTransferred]
0x180038bd1  cmp     eax, 40h ; '@'
0x180038bd4  jb      short loc_180038C33
0x180038bd6  mov     ecx, eax; unsigned __int64
0x180038bd8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180038bdd  mov     r14, rax
0x180038be0  test    rax, rax
0x180038be3  jnz     short loc_180038BF2
0x180038be5  mov     rcx, rdi; void *
0x180038be8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180038bed  jmp     loc_180038AA8
0x180038bf2  lea     rax, [rbp+NumberOfBytesTransferred]
0x180038bf6  mov     r9d, esi; nInBufferSize
0x180038bf9  mov     [rsp+50h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180038bfe  mov     r8, rdi; lpInBuffer
0x180038c01  mov     eax, [rbp+NumberOfBytesTransferred]
0x180038c04  mov     edx, 2F0003h; dwIoControlCode
0x180038c09  mov     [rsp+50h+var_28], eax; DWORD
0x180038c0d  mov     rcx, r12; hFile
0x180038c10  mov     [rsp+50h+var_30], r14; LPVOID
0x180038c15  call    KsSynchronousDeviceControl
0x180038c1a  mov     ebx, eax
0x180038c1c  test    eax, eax
0x180038c1e  js      short loc_180038C29
0x180038c20  mov     rax, [rbp+arg_8]
0x180038c24  mov     [rax], r14
0x180038c27  jmp     short loc_180038C38
0x180038c29  mov     rcx, r14; void *
0x180038c2c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180038c31  jmp     short loc_180038C38
0x180038c33  mov     ebx, 8000FFFFh
0x180038c38  mov     rcx, rdi; void *
0x180038c3b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180038c40  jmp     short loc_180038C47
0x180038c42  mov     ebx, 40103h
0x180038c47  mov     rcx, r15; pv
0x180038c4a  call    cs:__imp_CoTaskMemFree
0x180038c51  nop     dword ptr [rax+rax+00h]
0x180038c56  mov     eax, ebx
0x180038c58  mov     rbx, [rsp+50h+arg_10]
0x180038c60  add     rsp, 50h
0x180038c64  pop     r15
0x180038c66  pop     r14
0x180038c68  pop     r13
0x180038c6a  pop     r12
0x180038c6c  pop     rdi
0x180038c6d  pop     rsi
0x180038c6e  pop     rbp
0x180038c6f  retn
```
