# MFCreateFMPEG4MediaSink

- ea: `0x18002dcd0`
- end: `0x18002dec8`
- name: `MFCreateFMPEG4MediaSink`
- size: `504`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000f370`
- `0x1800104b0`
- `0x180010600`
- `0x180018064`
- `0x180018e70`
- `0x18002dcd0`
- `0x180034b38`
- `0x180065ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002dd25`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002dd25`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dd47`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002de07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002dd47`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002de07`

## string_xrefs

- `0x18002dcf3`: `MFCreateFMPEG4MediaSink_Stub`
- `0x18002dda5`: `MFCreateFMPEG4MediaSink_Stub`
- `0x18002de65`: `MFCreateFMPEG4MediaSink_Stub`

## pseudocode

```c
__int64 __fastcall MFCreateFMPEG4MediaSink(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  HRESULT Instance; // ebx
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  _BYTE v17[8]; // [rsp+30h] [rbp-38h] BYREF
  LPVOID ppv[6]; // [rsp+38h] [rbp-30h] BYREF

  ppv[0] = 0;
  sub_18000F370(v17, "MFCreateFMPEG4MediaSink_Stub", 234);
  Instance = CoCreateInstance(&stru_18006F208, 0, 1u, &stru_1800701F8, ppv);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int64, __int64))(*(_QWORD *)ppv[0] + 24LL))(
                 ppv[0],
                 a1,
                 a2,
                 a3,
                 a4);
    if ( Instance < 0 )
    {
      v13 = (__int64 *)qword_180084A30;
      if ( !qword_180084A30 )
      {
        v14 = MFGetCallStackTracingWeakReference();
        qword_180084A30 = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (__int64 *)qword_180084A30;
        }
        else
        {
          v13 = &qword_180083DB0;
          qword_180084A30 = (__int64)&qword_180083DB0;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v15 = sub_180010600();
        if ( *(_DWORD *)(v15 + 1996) != Instance )
          sub_180034B38(v15, "MFCreateFMPEG4MediaSink_Stub", 235, (unsigned int)Instance);
      }
      if ( byte_180084958 )
      {
        v12 = 15;
        goto LABEL_23;
      }
    }
  }
  else
  {
    v9 = (__int64 *)qword_180084A30;
    if ( !qword_180084A30 )
    {
      v10 = MFGetCallStackTracingWeakReference();
      qword_180084A30 = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v9 = (__int64 *)qword_180084A30;
      }
      else
      {
        v9 = &qword_180083DB0;
        qword_180084A30 = (__int64)&qword_180083DB0;
      }
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v11 = sub_180010600();
      if ( *(_DWORD *)(v11 + 1996) != Instance )
        sub_180034B38(v11, "MFCreateFMPEG4MediaSink_Stub", 234, (unsigned int)Instance);
    }
    if ( byte_180084958 )
    {
      v12 = 14;
LABEL_23:
      sub_180018E70(*((_QWORD *)RequestContext + 2), v12, qword_180070010, 0, Instance);
    }
  }
  sub_1800104B0(v17);
  sub_180018064(ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002dcd0  push    rbx
0x18002dcd2  push    rbp
0x18002dcd3  push    rsi
0x18002dcd4  push    rdi
0x18002dcd5  push    r14
0x18002dcd7  sub     rsp, 40h
0x18002dcdb  mov     rsi, r8
0x18002dcde  mov     [rsp+68h+var_30], 0
0x18002dce7  mov     rbp, rdx
0x18002dcea  mov     r14, rcx
0x18002dced  mov     r8d, 0EAh
0x18002dcf3  lea     rdx, aMfcreatefmpeg4_0; "MFCreateFMPEG4MediaSink_Stub"
0x18002dcfa  lea     rcx, [rsp+68h+var_38]
0x18002dcff  mov     rdi, r9
0x18002dd02  call    sub_18000F370
0x18002dd07  xor     edx, edx; pUnkOuter
0x18002dd09  lea     rax, [rsp+68h+var_30]
0x18002dd0e  lea     r9, stru_1800701F8; riid
0x18002dd15  mov     [rsp+68h+ppv], rax; ppv
0x18002dd1a  lea     rcx, stru_18006F208; rclsid
0x18002dd21  lea     r8d, [rdx+1]; dwClsContext
0x18002dd25  call    cs:CoCreateInstance
0x18002dd2c  nop     dword ptr [rax+rax+00h]
0x18002dd31  mov     ebx, eax
0x18002dd33  test    eax, eax
0x18002dd35  jns     loc_18002DDD1
0x18002dd3b  mov     rcx, cs:qword_180084A30
0x18002dd42  test    rcx, rcx
0x18002dd45  jnz     short loc_18002DD8F
0x18002dd47  call    cs:MFGetCallStackTracingWeakReference
0x18002dd4e  nop     dword ptr [rax+rax+00h]
0x18002dd53  mov     cs:qword_180084A30, rax
0x18002dd5a  mov     rcx, rax
0x18002dd5d  test    rax, rax
0x18002dd60  jz      short loc_18002DD81
0x18002dd62  mov     rax, [rax]
0x18002dd65  mov     edx, 7F0h
0x18002dd6a  mov     rax, [rax+8]
0x18002dd6e  call    cs:__guard_dispatch_icall_fptr
0x18002dd74  test    eax, eax
0x18002dd76  jz      short loc_18002DD81
0x18002dd78  mov     rcx, cs:qword_180084A30
0x18002dd7f  jmp     short loc_18002DD8F
0x18002dd81  lea     rcx, qword_180083DB0
0x18002dd88  mov     cs:qword_180084A30, rcx
0x18002dd8f  cmp     byte ptr [rcx+8], 0
0x18002dd93  jz      short loc_18002DDBA
0x18002dd95  call    sub_180010600
0x18002dd9a  cmp     [rax+7CCh], ebx
0x18002dda0  jz      short loc_18002DDBA
0x18002dda2  mov     r9d, ebx
0x18002dda5  lea     rdx, aMfcreatefmpeg4_0; "MFCreateFMPEG4MediaSink_Stub"
0x18002ddac  mov     r8d, 0EAh
0x18002ddb2  mov     rcx, rax
0x18002ddb5  call    sub_180034B38
0x18002ddba  cmp     cs:byte_180084958, 1
0x18002ddc1  jb      loc_18002DEA6
0x18002ddc7  mov     edx, 0Eh
0x18002ddcc  jmp     loc_18002DE88
0x18002ddd1  mov     rcx, [rsp+68h+var_30]
0x18002ddd6  mov     r9, rsi
0x18002ddd9  mov     r8, rbp
0x18002dddc  mov     [rsp+68h+ppv], rdi
0x18002dde1  mov     rdx, r14
0x18002dde4  mov     rax, [rcx]
0x18002dde7  mov     rax, [rax+18h]
0x18002ddeb  call    cs:__guard_dispatch_icall_fptr
0x18002ddf1  mov     ebx, eax
0x18002ddf3  test    eax, eax
0x18002ddf5  jns     loc_18002DEA6
0x18002ddfb  mov     rcx, cs:qword_180084A30
0x18002de02  test    rcx, rcx
0x18002de05  jnz     short loc_18002DE4F
0x18002de07  call    cs:MFGetCallStackTracingWeakReference
0x18002de0e  nop     dword ptr [rax+rax+00h]
0x18002de13  mov     cs:qword_180084A30, rax
0x18002de1a  mov     rcx, rax
0x18002de1d  test    rax, rax
0x18002de20  jz      short loc_18002DE41
0x18002de22  mov     rax, [rax]
0x18002de25  mov     edx, 7F0h
0x18002de2a  mov     rax, [rax+8]
0x18002de2e  call    cs:__guard_dispatch_icall_fptr
0x18002de34  test    eax, eax
0x18002de36  jz      short loc_18002DE41
0x18002de38  mov     rcx, cs:qword_180084A30
0x18002de3f  jmp     short loc_18002DE4F
0x18002de41  lea     rcx, qword_180083DB0
0x18002de48  mov     cs:qword_180084A30, rcx
0x18002de4f  cmp     byte ptr [rcx+8], 0
0x18002de53  jz      short loc_18002DE7A
0x18002de55  call    sub_180010600
0x18002de5a  cmp     [rax+7CCh], ebx
0x18002de60  jz      short loc_18002DE7A
0x18002de62  mov     r9d, ebx
0x18002de65  lea     rdx, aMfcreatefmpeg4_0; "MFCreateFMPEG4MediaSink_Stub"
0x18002de6c  mov     r8d, 0EBh
0x18002de72  mov     rcx, rax
0x18002de75  call    sub_180034B38
0x18002de7a  cmp     cs:byte_180084958, 1
0x18002de81  jb      short loc_18002DEA6
0x18002de83  mov     edx, 0Fh
0x18002de88  mov     rcx, cs:RequestContext
0x18002de8f  lea     r8, qword_180070010
0x18002de96  xor     r9d, r9d
0x18002de99  mov     dword ptr [rsp+68h+ppv], ebx
0x18002de9d  mov     rcx, [rcx+10h]
0x18002dea1  call    sub_180018E70
0x18002dea6  lea     rcx, [rsp+68h+var_38]
0x18002deab  call    sub_1800104B0
0x18002deb0  lea     rcx, [rsp+68h+var_30]
0x18002deb5  call    sub_180018064
0x18002deba  mov     eax, ebx
0x18002debc  add     rsp, 40h
0x18002dec0  pop     r14
0x18002dec2  pop     rdi
0x18002dec3  pop     rsi
0x18002dec4  pop     rbp
0x18002dec5  pop     rbx
0x18002dec6  retn
```
