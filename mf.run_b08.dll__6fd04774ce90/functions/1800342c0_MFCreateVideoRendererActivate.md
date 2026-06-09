# MFCreateVideoRendererActivate

- ea: `0x1800342c0`
- end: `0x180034495`
- name: `MFCreateVideoRendererActivate`
- size: `469`
- prototype: `HRESULT __stdcall(HWND hwndVideo, IMFActivate **ppActivate)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x18000f370`
- `0x1800104b0`
- `0x180010600`
- `0x180018064`
- `0x180018e70`
- `0x180032be8`
- `0x1800342c0`
- `0x180034b38`
- `0x180065ec0`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003430a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800343dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003430a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800343dc`

## string_xrefs

- `0x1800342d9`: `MFCreateVideoRendererActivate`
- `0x180034368`: `MFCreateVideoRendererActivate`
- `0x18003443a`: `MFCreateVideoRendererActivate`

## pseudocode

```c
HRESULT __stdcall MFCreateVideoRendererActivate(HWND hwndVideo, IMFActivate **ppActivate)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  HRESULT v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  char v14; // [rsp+48h] [rbp+10h] BYREF
  IMFActivate *v15; // [rsp+50h] [rbp+18h] BYREF

  v15 = 0;
  sub_18000F370(&v14, "MFCreateVideoRendererActivate", 38);
  if ( ppActivate )
  {
    *ppActivate = 0;
    v6 = sub_180032BE8(hwndVideo, v4, &v15);
    if ( v6 >= 0 )
    {
      *ppActivate = v15;
      v15 = 0;
      goto LABEL_25;
    }
    v10 = (__int64 *)qword_180084A30;
    if ( !qword_180084A30 )
    {
      v11 = MFGetCallStackTracingWeakReference(0);
      qword_180084A30 = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)qword_180084A30;
      }
      else
      {
        v10 = &qword_180083DB0;
        qword_180084A30 = (__int64)&qword_180083DB0;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = sub_180010600();
      if ( *(_DWORD *)(v12 + 1996) != v6 )
        sub_180034B38(v12, "MFCreateVideoRendererActivate", 45, (unsigned int)v6);
    }
    if ( byte_180084958 )
    {
      v9 = 11;
      goto LABEL_12;
    }
  }
  else
  {
    v5 = (__int64 *)qword_180084A30;
    v6 = -2147467261;
    if ( !qword_180084A30 )
    {
      v7 = MFGetCallStackTracingWeakReference(0);
      qword_180084A30 = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v5 = (__int64 *)qword_180084A30;
      }
      else
      {
        v5 = &qword_180083DB0;
        qword_180084A30 = (__int64)&qword_180083DB0;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v8 = sub_180010600();
      if ( *(_DWORD *)(v8 + 1996) != -2147467261 )
        sub_180034B38(v8, "MFCreateVideoRendererActivate", 38, 2147500035LL);
    }
    if ( byte_180084958 )
    {
      v9 = 10;
LABEL_12:
      sub_180018E70(*((_QWORD *)RequestContext + 2), v9, &unk_180070768, 0, v6);
    }
  }
LABEL_25:
  sub_1800104B0();
  sub_180018064(&v15);
  return v6;
}

```

## disassembly

```asm
0x1800342c0  mov     [rsp+arg_0], rbx
0x1800342c5  push    rdi
0x1800342c6  sub     rsp, 30h
0x1800342ca  mov     rdi, rdx
0x1800342cd  mov     [rsp+38h+arg_10], 0
0x1800342d6  mov     rbx, rcx
0x1800342d9  lea     rdx, aMfcreatevideor_1; "MFCreateVideoRendererActivate"
0x1800342e0  lea     rcx, [rsp+38h+arg_8]
0x1800342e5  mov     r8d, 26h ; '&'
0x1800342eb  call    sub_18000F370
0x1800342f0  test    rdi, rdi
0x1800342f3  jnz     loc_1800343B2
0x1800342f9  mov     rcx, cs:qword_180084A30
0x180034300  mov     ebx, 80004003h
0x180034305  test    rcx, rcx
0x180034308  jnz     short loc_180034352
0x18003430a  call    cs:MFGetCallStackTracingWeakReference
0x180034311  nop     dword ptr [rax+rax+00h]
0x180034316  mov     cs:qword_180084A30, rax
0x18003431d  mov     rcx, rax
0x180034320  test    rax, rax
0x180034323  jz      short loc_180034344
0x180034325  mov     rax, [rax]
0x180034328  mov     edx, 7F0h
0x18003432d  mov     rax, [rax+8]
0x180034331  call    cs:__guard_dispatch_icall_fptr
0x180034337  test    eax, eax
0x180034339  jz      short loc_180034344
0x18003433b  mov     rcx, cs:qword_180084A30
0x180034342  jmp     short loc_180034352
0x180034344  lea     rcx, qword_180083DB0
0x18003434b  mov     cs:qword_180084A30, rcx
0x180034352  cmp     byte ptr [rcx+8], 0
0x180034356  jz      short loc_18003437D
0x180034358  call    sub_180010600
0x18003435d  cmp     [rax+7CCh], ebx
0x180034363  jz      short loc_18003437D
0x180034365  mov     r9d, ebx
0x180034368  lea     rdx, aMfcreatevideor_1; "MFCreateVideoRendererActivate"
0x18003436f  mov     r8d, 26h ; '&'
0x180034375  mov     rcx, rax
0x180034378  call    sub_180034B38
0x18003437d  cmp     cs:byte_180084958, 1
0x180034384  jb      loc_180034473
0x18003438a  mov     edx, 0Ah
0x18003438f  mov     rcx, cs:RequestContext
0x180034396  lea     r8, unk_180070768
0x18003439d  xor     r9d, r9d
0x1800343a0  mov     [rsp+38h+var_18], ebx
0x1800343a4  mov     rcx, [rcx+10h]
0x1800343a8  call    sub_180018E70
0x1800343ad  jmp     loc_180034473
0x1800343b2  lea     r8, [rsp+38h+arg_10]
0x1800343b7  mov     qword ptr [rdi], 0
0x1800343be  mov     rcx, rbx
0x1800343c1  call    sub_180032BE8
0x1800343c6  mov     ebx, eax
0x1800343c8  test    eax, eax
0x1800343ca  jns     loc_180034462
0x1800343d0  mov     rcx, cs:qword_180084A30
0x1800343d7  test    rcx, rcx
0x1800343da  jnz     short loc_180034424
0x1800343dc  call    cs:MFGetCallStackTracingWeakReference
0x1800343e3  nop     dword ptr [rax+rax+00h]
0x1800343e8  mov     cs:qword_180084A30, rax
0x1800343ef  mov     rcx, rax
0x1800343f2  test    rax, rax
0x1800343f5  jz      short loc_180034416
0x1800343f7  mov     rax, [rax]
0x1800343fa  mov     edx, 7F0h
0x1800343ff  mov     rax, [rax+8]
0x180034403  call    cs:__guard_dispatch_icall_fptr
0x180034409  test    eax, eax
0x18003440b  jz      short loc_180034416
0x18003440d  mov     rcx, cs:qword_180084A30
0x180034414  jmp     short loc_180034424
0x180034416  lea     rcx, qword_180083DB0
0x18003441d  mov     cs:qword_180084A30, rcx
0x180034424  cmp     byte ptr [rcx+8], 0
0x180034428  jz      short loc_18003444F
0x18003442a  call    sub_180010600
0x18003442f  cmp     [rax+7CCh], ebx
0x180034435  jz      short loc_18003444F
0x180034437  mov     r9d, ebx
0x18003443a  lea     rdx, aMfcreatevideor_1; "MFCreateVideoRendererActivate"
0x180034441  mov     r8d, 2Dh ; '-'
0x180034447  mov     rcx, rax
0x18003444a  call    sub_180034B38
0x18003444f  cmp     cs:byte_180084958, 1
0x180034456  jb      short loc_180034473
0x180034458  mov     edx, 0Bh
0x18003445d  jmp     loc_18003438F
0x180034462  mov     rax, [rsp+38h+arg_10]
0x180034467  mov     [rdi], rax
0x18003446a  mov     [rsp+38h+arg_10], 0
0x180034473  lea     rcx, [rsp+38h+arg_8]
0x180034478  call    sub_1800104B0
0x18003447d  lea     rcx, [rsp+38h+arg_10]
0x180034482  call    sub_180018064
0x180034487  mov     eax, ebx
0x180034489  mov     rbx, [rsp+38h+arg_0]
0x18003448e  add     rsp, 30h
0x180034492  pop     rdi
0x180034493  retn
```
