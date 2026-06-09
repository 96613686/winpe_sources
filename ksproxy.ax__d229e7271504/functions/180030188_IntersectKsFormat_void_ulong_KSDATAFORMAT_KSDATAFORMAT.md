# IntersectKsFormat(void *,ulong,KSDATAFORMAT *,KSDATAFORMAT * *)

- ea: `0x180030188`
- end: `0x1800304ee`
- name: `?IntersectKsFormat@@YAJPEAXKPEATKSDATAFORMAT@@PEAPEAT1@@Z`
- size: `870`
- prototype: `__int64 __fastcall(char *hFile, int, union KSDATAFORMAT *, union KSDATAFORMAT **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x180031844`

## callees

- `0x1800063a0`
- `0x18000bde0`
- `0x18001cf28`
- `0x18001f1c4`
- `0x18001f210`
- `0x180025860`
- `0x180030188`
- `0x180044850`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180030416`
- `ole32!CoTaskMemAlloc` at `0x180030416`
- `ole32!CoTaskMemFree` at `0x18003049d`
- `ole32!CoTaskMemFree` at `0x1800304b0`
- `ole32!CoTaskMemFree` at `0x18003049d`
- `ole32!CoTaskMemFree` at `0x1800304b0`

## pseudocode

```c
__int64 __fastcall IntersectKsFormat(char *hFile, int a2, union KSDATAFORMAT *a3, union KSDATAFORMAT **a4)
{
  LONGLONG v5; // rax
  ULONG Reserved; // r12d
  unsigned int Data1; // r13d
  LONGLONG v10; // rax
  _DWORD *v11; // rsi
  __int64 result; // rax
  union KSDATAFORMAT *v13; // r14
  int v14; // r15d
  unsigned int v15; // ecx
  bool v16; // cc
  GUID *v17; // rax
  GUID *v18; // rdi
  int v19; // ecx
  LONGLONG v20; // rax
  LONGLONG v21; // rax
  signed int v22; // eax
  unsigned int v23; // eax
  union KSDATAFORMAT *v24; // rax
  unsigned int v25; // ebx
  unsigned int cb; // [rsp+40h] [rbp-28h] BYREF
  unsigned int cb_4; // [rsp+44h] [rbp-24h]
  __int64 v28; // [rsp+48h] [rbp-20h]
  union KSDATAFORMAT *v29; // [rsp+50h] [rbp-18h]
  LPVOID pv; // [rsp+C0h] [rbp+58h] BYREF
  union KSDATAFORMAT **v33; // [rsp+C8h] [rbp+60h]

  v33 = a4;
  v5 = *(&a3->Alignment + 6) - *(_QWORD *)&FORMAT_VideoInfo.Data1;
  pv = 0;
  if ( !v5 )
    v5 = *(&a3->Alignment + 7) - *(_QWORD *)FORMAT_VideoInfo.Data4;
  if ( v5 )
  {
    v10 = *(&a3->Alignment + 6) - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
    if ( !v10 )
      v10 = *(&a3->Alignment + 7) - *(_QWORD *)FORMAT_VideoInfo2.Data4;
    if ( v10 )
      return 2147942487LL;
    Reserved = a3[2].Reserved;
    Data1 = a3[2].MajorFormat.Data1;
  }
  else
  {
    Reserved = *((_DWORD *)&a3[1].Alignment + 13);
    Data1 = *((_DWORD *)&a3[1].Alignment + 14);
  }
  v28 = *(&a3[1].Alignment + 5);
  if ( (int)KsGetMultiplePinFactoryItems(hFile, a2, 13, &pv) >= 0 && (v11 = pv) != 0
    || (result = KsGetMultiplePinFactoryItems(hFile, a2, 3, &pv), (int)result >= 0) && (v11 = pv) != 0 )
  {
    v13 = (union KSDATAFORMAT *)(v11 + 2);
    v14 = 0;
    v29 = 0;
    v15 = 0;
    while ( 1 )
    {
      cb_4 = v15;
      if ( v14 || v15 >= v11[1] )
      {
        CoTaskMemFree(v11);
        if ( !v14 )
          return 2147500037LL;
        *v33 = v29;
        return 0;
      }
      v16 = v13->FormatSize <= 0xF4240;
      LODWORD(pv) = 0;
      if ( !v16 )
      {
        v25 = -2147024809;
        goto LABEL_44;
      }
      if ( (int)IsFormatInRange(v13, a3) >= 0 )
        break;
LABEL_40:
      v15 = cb_4 + 1;
      v13 = (union KSDATAFORMAT *)((char *)v13 + ((v13->FormatSize + 7) & 0xFFFFFFF8));
    }
    v17 = (GUID *)operator new[](v13->FormatSize + 40LL);
    v18 = v17;
    if ( !v17 )
      goto LABEL_42;
    v17[1].Data1 = 4;
    *(_DWORD *)&v17[1].Data2 = 1;
    *v17 = GUID_8c134960_51ad_11cf_878a_94f801c10000;
    *(_DWORD *)v17[1].Data4 = a2;
    *(_DWORD *)&v17[1].Data4[4] = 0;
    v19 = v13->FormatSize + 8;
    *(_DWORD *)&v17[2].Data2 = 1;
    v17[2].Data1 = v19;
    memcpy_0(v17[2].Data4, v13, v13->FormatSize);
    v20 = *(&a3->Alignment + 6) - *(_QWORD *)&FORMAT_VideoInfo.Data1;
    if ( !v20 )
      v20 = *(&a3->Alignment + 7) - *(_QWORD *)FORMAT_VideoInfo.Data4;
    if ( v20 )
    {
      v21 = *(&a3->Alignment + 6) - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
      if ( !v21 )
        v21 = *(&a3->Alignment + 7) - *(_QWORD *)FORMAT_VideoInfo2.Data4;
      if ( v21 )
      {
LABEL_28:
        v22 = KsSynchronousDeviceControl(hFile, 0x2F0003u, v18, v13->FormatSize + 40, 0, 0, (LPDWORD)&pv);
        if ( v22 != -2147024774 )
          goto LABEL_33;
        cb = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x33u, &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids);
        v22 = KsSynchronousDeviceControl(hFile, 0x2F0003u, v18, v13->FormatSize + 40, &cb, 4u, (LPDWORD)&pv);
        if ( v22 >= 0 )
        {
          v23 = cb;
          LODWORD(pv) = cb;
        }
        else
        {
LABEL_33:
          if ( v22 != -2147024662 )
          {
LABEL_39:
            operator delete(v18);
            goto LABEL_40;
          }
          v23 = (unsigned int)pv;
        }
        if ( v23 >= 0x40 )
        {
          v24 = (union KSDATAFORMAT *)CoTaskMemAlloc(v23);
          v29 = v24;
          if ( !v24 )
          {
            operator delete(v18);
LABEL_42:
            v25 = -2147024882;
LABEL_44:
            CoTaskMemFree(v11);
            return v25;
          }
          if ( KsSynchronousDeviceControl(hFile, 0x2F0003u, v18, v13->FormatSize + 40, v24, (DWORD)pv, (LPDWORD)&pv) >= 0 )
            v14 = 1;
        }
        goto LABEL_39;
      }
      *(_DWORD *)&v18[20].Data2 = Reserved;
      *(_DWORD *)v18[20].Data4 = Data1;
    }
    else
    {
      *(_DWORD *)&v18[18].Data4[4] = Reserved;
      v18[19].Data1 = Data1;
    }
    *(_QWORD *)&v18[18].Data1 = v28;
    goto LABEL_28;
  }
  return result;
}

```

## disassembly

```asm
0x180030188  mov     [rsp-40h+arg_18], r9
0x18003018d  mov     [rsp-40h+arg_8], edx
0x180030191  mov     [rsp-40h+hFile], rcx
0x180030196  push    rbp
0x180030197  push    rbx
0x180030198  push    rsi
0x180030199  push    rdi
0x18003019a  push    r12
0x18003019c  push    r13
0x18003019e  push    r14
0x1800301a0  push    r15
0x1800301a2  mov     rbp, rsp
0x1800301a5  sub     rsp, 68h
0x1800301a9  mov     rax, [r8+30h]
0x1800301ad  mov     rbx, r8
0x1800301b0  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x1800301b7  mov     r14d, edx
0x1800301ba  mov     rdi, rcx
0x1800301bd  mov     [rbp+pv], 0
0x1800301c5  jnz     short loc_1800301D2
0x1800301c7  mov     rax, [r8+38h]
0x1800301cb  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x1800301d2  test    rax, rax
0x1800301d5  jnz     short loc_1800301E1
0x1800301d7  mov     r12d, [r8+74h]
0x1800301db  mov     r13d, [r8+78h]
0x1800301df  jmp     short loc_180030210
0x1800301e1  mov     rax, [r8+30h]
0x1800301e5  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800301ec  jnz     short loc_1800301F9
0x1800301ee  mov     rax, [r8+38h]
0x1800301f2  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800301f9  test    rax, rax
0x1800301fc  jnz     loc_1800304D7
0x180030202  mov     r12d, [r8+8Ch]
0x180030209  mov     r13d, [r8+90h]
0x180030210  mov     rax, [r8+68h]
0x180030214  lea     r9, [rbp+pv]
0x180030218  mov     r8d, 0Dh
0x18003021e  mov     [rbp+var_20], rax
0x180030222  call    KsGetMultiplePinFactoryItems
0x180030227  test    eax, eax
0x180030229  js      short loc_180030234
0x18003022b  mov     rsi, [rbp+pv]
0x18003022f  test    rsi, rsi
0x180030232  jnz     short loc_18003025E
0x180030234  lea     r9, [rbp+pv]
0x180030238  mov     r8d, 3
0x18003023e  mov     edx, r14d
0x180030241  mov     rcx, rdi; hFile
0x180030244  call    KsGetMultiplePinFactoryItems
0x180030249  test    eax, eax
0x18003024b  js      loc_1800304DC
0x180030251  mov     rsi, [rbp+pv]
0x180030255  test    rsi, rsi
0x180030258  jz      loc_1800304DC
0x18003025e  xor     eax, eax
0x180030260  lea     r14, [rsi+8]
0x180030264  xor     r15d, r15d
0x180030267  mov     [rbp+var_18], rax
0x18003026b  xor     ecx, ecx
0x18003026d  mov     dword ptr [rbp+cb+4], ecx
0x180030270  test    r15d, r15d
0x180030273  jnz     loc_1800304AD
0x180030279  cmp     ecx, [rsi+4]
0x18003027c  jnb     loc_1800304AD
0x180030282  cmp     dword ptr [r14], 0F4240h
0x180030289  mov     dword ptr [rbp+pv], r15d
0x18003028d  ja      loc_180030495
0x180030293  mov     rdx, rbx; union KSDATAFORMAT *
0x180030296  mov     rcx, r14; union KSDATAFORMAT *
0x180030299  call    ?IsFormatInRange@@YAJPEATKSDATAFORMAT@@0@Z; IsFormatInRange(KSDATAFORMAT *,KSDATAFORMAT *)
0x18003029e  test    eax, eax
0x1800302a0  js      loc_18003046B
0x1800302a6  mov     ecx, [r14]
0x1800302a9  add     rcx, 28h ; '('; unsigned __int64
0x1800302ad  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800302b2  mov     rdi, rax
0x1800302b5  test    rax, rax
0x1800302b8  jz      loc_18003048E
0x1800302be  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x1800302c5  mov     dword ptr [rax+10h], 4
0x1800302cc  lea     edx, [r15+1]
0x1800302d0  mov     [rax+14h], edx
0x1800302d3  movdqu  xmmword ptr [rax], xmm0
0x1800302d7  mov     eax, [rbp+arg_8]
0x1800302da  mov     [rdi+18h], eax
0x1800302dd  mov     [rdi+1Ch], r15d
0x1800302e1  mov     ecx, [r14]
0x1800302e4  add     ecx, 8
0x1800302e7  mov     [rdi+24h], edx
0x1800302ea  mov     [rdi+20h], ecx
0x1800302ed  mov     rdx, r14; Src
0x1800302f0  mov     r8d, [r14]; Size
0x1800302f3  lea     rcx, [rdi+28h]; void *
0x1800302f7  call    memcpy_0
0x1800302fc  mov     rax, [rbx+30h]
0x180030300  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x180030307  jnz     short loc_180030314
0x180030309  mov     rax, [rbx+38h]
0x18003030d  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180030314  test    rax, rax
0x180030317  jnz     short loc_180030329
0x180030319  mov     [rdi+12Ch], r12d
0x180030320  mov     [rdi+130h], r13d
0x180030327  jmp     short loc_180030354
0x180030329  mov     rax, [rbx+30h]
0x18003032d  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180030334  jnz     short loc_180030341
0x180030336  mov     rax, [rbx+38h]
0x18003033a  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180030341  test    rax, rax
0x180030344  jnz     short loc_18003035F
0x180030346  mov     [rdi+144h], r12d
0x18003034d  mov     [rdi+148h], r13d
0x180030354  mov     rax, [rbp+var_20]
0x180030358  mov     [rdi+120h], rax
0x18003035f  mov     r9d, [r14]
0x180030362  lea     rax, [rbp+pv]
0x180030366  mov     rcx, [rbp+hFile]; hFile
0x18003036a  add     r9d, 28h ; '('; nInBufferSize
0x18003036e  mov     [rsp+68h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180030373  mov     r8, rdi; lpInBuffer
0x180030376  mov     [rsp+68h+var_40], 0; DWORD
0x18003037e  mov     edx, 2F0003h; dwIoControlCode
0x180030383  mov     [rsp+68h+var_48], 0; LPVOID
0x18003038c  call    KsSynchronousDeviceControl
0x180030391  cmp     eax, 8007007Ah
0x180030396  jnz     short loc_180030405
0x180030398  mov     dword ptr [rbp+cb], 0
0x18003039f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800303a6  lea     rax, WPP_GLOBAL_Control
0x1800303ad  cmp     rcx, rax
0x1800303b0  jz      short loc_1800303C7
0x1800303b2  mov     rcx, [rcx+10h]
0x1800303b6  lea     r8, WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids
0x1800303bd  mov     edx, 33h ; '3'
0x1800303c2  call    WPP_SF_
0x1800303c7  mov     r9d, [r14]
0x1800303ca  lea     rax, [rbp+pv]
0x1800303ce  mov     rcx, [rbp+hFile]; hFile
0x1800303d2  add     r9d, 28h ; '('; nInBufferSize
0x1800303d6  mov     [rsp+68h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x1800303db  mov     r8, rdi; lpInBuffer
0x1800303de  lea     rax, [rbp+cb]
0x1800303e2  mov     [rsp+68h+var_40], 4; DWORD
0x1800303ea  mov     edx, 2F0003h; dwIoControlCode
0x1800303ef  mov     [rsp+68h+var_48], rax; LPVOID
0x1800303f4  call    KsSynchronousDeviceControl
0x1800303f9  test    eax, eax
0x1800303fb  js      short loc_180030405
0x1800303fd  mov     eax, dword ptr [rbp+cb]
0x180030400  mov     dword ptr [rbp+pv], eax
0x180030403  jmp     short loc_18003040F
0x180030405  cmp     eax, 800700EAh
0x18003040a  jnz     short loc_180030463
0x18003040c  mov     eax, dword ptr [rbp+pv]
0x18003040f  cmp     eax, 40h ; '@'
0x180030412  jb      short loc_180030463
0x180030414  mov     ecx, eax; cb
0x180030416  call    cs:__imp_CoTaskMemAlloc
0x18003041d  nop     dword ptr [rax+rax+00h]
0x180030422  mov     [rbp+var_18], rax
0x180030426  test    rax, rax
0x180030429  jz      short loc_180030486
0x18003042b  mov     r9d, [r14]
0x18003042e  lea     rcx, [rbp+pv]
0x180030432  mov     [rsp+68h+lpNumberOfBytesTransferred], rcx; lpNumberOfBytesTransferred
0x180030437  add     r9d, 28h ; '('; nInBufferSize
0x18003043b  mov     ecx, dword ptr [rbp+pv]
0x18003043e  mov     r8, rdi; lpInBuffer
0x180030441  mov     [rsp+68h+var_40], ecx; DWORD
0x180030445  mov     edx, 2F0003h; dwIoControlCode
0x18003044a  mov     rcx, [rbp+hFile]; hFile
0x18003044e  mov     [rsp+68h+var_48], rax; LPVOID
0x180030453  call    KsSynchronousDeviceControl
0x180030458  test    eax, eax
0x18003045a  mov     eax, 1
0x18003045f  cmovns  r15d, eax
0x180030463  mov     rcx, rdi; void *
0x180030466  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003046b  mov     eax, [r14]
0x18003046e  mov     edx, 0FFFFFFF8h
0x180030473  mov     ecx, dword ptr [rbp+cb+4]
0x180030476  add     eax, 7
0x180030479  and     rax, rdx
0x18003047c  inc     ecx
0x18003047e  add     r14, rax
0x180030481  jmp     loc_18003026D
0x180030486  mov     rcx, rdi; void *
0x180030489  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003048e  mov     ebx, 8007000Eh
0x180030493  jmp     short loc_18003049A
0x180030495  mov     ebx, 80070057h
0x18003049a  mov     rcx, rsi; pv
0x18003049d  call    cs:__imp_CoTaskMemFree
0x1800304a4  nop     dword ptr [rax+rax+00h]
0x1800304a9  mov     eax, ebx
0x1800304ab  jmp     short loc_1800304DC
0x1800304ad  mov     rcx, rsi; pv
0x1800304b0  call    cs:__imp_CoTaskMemFree
0x1800304b7  nop     dword ptr [rax+rax+00h]
0x1800304bc  test    r15d, r15d
0x1800304bf  jz      short loc_1800304D0
0x1800304c1  mov     rax, [rbp+var_18]
0x1800304c5  mov     rcx, [rbp+arg_18]
0x1800304c9  mov     [rcx], rax
0x1800304cc  xor     eax, eax
0x1800304ce  jmp     short loc_1800304DC
0x1800304d0  mov     eax, 80004005h
0x1800304d5  jmp     short loc_1800304DC
0x1800304d7  mov     eax, 80070057h
0x1800304dc  add     rsp, 68h
0x1800304e0  pop     r15
0x1800304e2  pop     r14
0x1800304e4  pop     r13
0x1800304e6  pop     r12
0x1800304e8  pop     rdi
0x1800304e9  pop     rsi
0x1800304ea  pop     rbx
0x1800304eb  pop     rbp
0x1800304ec  retn
```
