# NDXGI::CDevice::ETWWriteSubmitCommandCB(uint,_D3DDDICB_SUBMITCOMMAND const *)

- ea: `0x1800806c8`
- end: `0x180080951`
- name: `?ETWWriteSubmitCommandCB@CDevice@NDXGI@@QEBAJIPEBU_D3DDDICB_SUBMITCOMMAND@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(NDXGI::CDevice *__hidden this, unsigned int, const struct _D3DDDICB_SUBMITCOMMAND *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021700`

## callees

- `0x1800806c8`
- `0x1800a9d20`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800808d1`
- `ntdll!EtwEventWrite` at `0x1800808d1`

## pseudocode

```c
__int64 __fastcall NDXGI::CDevice::ETWWriteSubmitCommandCB(
        NDXGI::CDevice *this,
        int a2,
        const struct _D3DDDICB_SUBMITCOMMAND *a3)
{
  _DWORD *v4; // r9
  _DWORD *v5; // r10
  _DWORD *v6; // r11
  unsigned int v7; // eax
  _DWORD *v8; // rbx
  unsigned int v9; // ecx
  char *v10; // rdi
  char *v11; // rax
  int v12; // r12d
  unsigned int v13; // r14d
  __int64 v14; // rdx
  char v16; // [rsp+28h] [rbp-E0h] BYREF
  _QWORD v17[23]; // [rsp+38h] [rbp-D0h] BYREF
  int v18; // [rsp+F0h] [rbp-18h]
  int v19; // [rsp+F4h] [rbp-14h]
  __int64 v20; // [rsp+F8h] [rbp-10h]
  int v21; // [rsp+100h] [rbp-8h]
  int v22; // [rsp+104h] [rbp-4h]
  __int64 v23; // [rsp+108h] [rbp+0h]
  int v24; // [rsp+110h] [rbp+8h]
  int v25; // [rsp+114h] [rbp+Ch]
  __int64 v26; // [rsp+118h] [rbp+10h]
  int v27; // [rsp+120h] [rbp+18h]
  int v28; // [rsp+124h] [rbp+1Ch]
  _DWORD v29[64]; // [rsp+128h] [rbp+20h] BYREF
  int v30; // [rsp+270h] [rbp+168h] BYREF

  v30 = a2;
  if ( *((_DWORD *)a3 + 4) > 0x40u )
    return 2147942487LL;
  if ( *((_DWORD *)a3 + 154) != 1 )
  {
    if ( *((_DWORD *)a3 + 154) == 2 )
    {
      v10 = (char *)a3 + 624;
      if ( !*((_DWORD *)a3 + 156) )
      {
        v4 = (_DWORD *)((char *)a3 + 628);
        if ( !*((_DWORD *)a3 + 157) )
        {
          v5 = (_DWORD *)((char *)a3 + 632);
          if ( !*((_DWORD *)a3 + 158) )
          {
            v6 = (_DWORD *)((char *)a3 + 636);
            if ( !*((_DWORD *)a3 + 159) )
            {
              v8 = (_DWORD *)((char *)a3 + 640);
              if ( !*((_DWORD *)a3 + 160) )
                goto LABEL_9;
            }
          }
        }
      }
    }
    return 2147942487LL;
  }
  v4 = (_DWORD *)((char *)a3 + 628);
  if ( *((_DWORD *)a3 + 157) > 0x1FECu )
    return 2147942487LL;
  v5 = (_DWORD *)((char *)a3 + 632);
  if ( *((_DWORD *)a3 + 158) > 0x1FECu )
    return 2147942487LL;
  v6 = (_DWORD *)((char *)a3 + 636);
  v7 = *((_DWORD *)a3 + 159);
  if ( v7 > 0x1FEC )
    return 2147942487LL;
  v8 = (_DWORD *)((char *)a3 + 640);
  v9 = *((_DWORD *)a3 + 160);
  if ( v9 > 0x1FEC || *v4 + *v5 + v9 + v7 > 0x1FEC )
    return 2147942487LL;
  v10 = (char *)a3 + 624;
LABEL_9:
  v11 = (char *)this + 80;
  v12 = *((unsigned __int8 *)a3 + 16);
  v13 = 0;
  v17[0] = v11;
  v17[1] = 8;
  v17[2] = &v30;
  v17[4] = &v16;
  v17[3] = 4;
  v16 = v12;
  for ( v17[5] = 1; v13 < *((_DWORD *)a3 + 4); v29[v14] = *(_DWORD *)(*((_QWORD *)a3 + v14 + 3) + 8LL) )
    v14 = v13++;
  v17[6] = v29;
  v17[14] = v4;
  v17[7] = (unsigned int)(4 * v12);
  v17[10] = (char *)a3 + 620;
  v17[22] = *((_QWORD *)a3 + 81);
  v18 = 4 * *v4;
  v20 = *((_QWORD *)a3 + 82);
  v21 = 4 * *v5;
  v23 = *((_QWORD *)a3 + 83);
  v24 = 4 * *v6;
  v26 = *((_QWORD *)a3 + 84);
  v27 = 4 * *v8;
  v17[8] = (char *)a3 + 616;
  v17[9] = 4;
  v17[11] = 4;
  v17[12] = v10;
  v17[13] = 4;
  v17[15] = 4;
  v17[16] = v5;
  v17[17] = 4;
  v17[18] = v6;
  v17[19] = 4;
  v17[20] = v8;
  v17[21] = 4;
  v19 = 0;
  v22 = 0;
  v25 = 0;
  v28 = 0;
  EtwEventWrite(Direct3D11EtwProviderGuid_Context, ")", 15, v17);
  return 0;
}

```

## disassembly

```asm
0x1800806c8  mov     rax, rsp
0x1800806cb  mov     [rax+8], rbx
0x1800806cf  mov     [rax+18h], rsi
0x1800806d3  mov     [rax+10h], edx
0x1800806d6  push    rbp
0x1800806d7  push    rdi
0x1800806d8  push    r12
0x1800806da  push    r13
0x1800806dc  push    r14
0x1800806de  lea     rbp, [rax-158h]
0x1800806e5  sub     rsp, 230h
0x1800806ec  mov     rax, cs:__security_cookie
0x1800806f3  xor     rax, rsp
0x1800806f6  mov     [rbp+150h+var_30], rax
0x1800806fd  cmp     dword ptr [r8+10h], 40h ; '@'
0x180080702  mov     r14, rcx
0x180080705  ja      loc_180080909
0x18008070b  lea     rsi, [r8+268h]
0x180080712  xor     r13d, r13d
0x180080715  mov     edx, [rsi]
0x180080717  sub     edx, 1
0x18008071a  jnz     loc_180080904
0x180080720  lea     r9, [r8+274h]
0x180080727  mov     edx, 1FECh
0x18008072c  cmp     [r9], edx
0x18008072f  ja      loc_180080909
0x180080735  lea     r10, [r8+278h]
0x18008073c  cmp     [r10], edx
0x18008073f  ja      loc_180080909
0x180080745  lea     r11, [r8+27Ch]
0x18008074c  mov     eax, [r11]
0x18008074f  cmp     eax, edx
0x180080751  ja      loc_180080909
0x180080757  lea     rbx, [r8+280h]
0x18008075e  mov     ecx, [rbx]
0x180080760  cmp     ecx, edx
0x180080762  ja      loc_180080909
0x180080768  add     eax, ecx
0x18008076a  add     eax, [r10]
0x18008076d  add     eax, [r9]
0x180080770  cmp     eax, edx
0x180080772  ja      loc_180080909
0x180080778  lea     rdi, [r8+270h]
0x18008077f  lea     rax, [r14+50h]
0x180080783  movzx   r12d, byte ptr [r8+10h]
0x180080788  mov     r14d, r13d
0x18008078b  mov     [rsp+250h+var_220], rax
0x180080790  lea     rax, [rbp+150h+arg_8]
0x180080797  mov     [rsp+250h+var_218], 8
0x1800807a0  mov     [rsp+250h+var_210], rax
0x1800807a5  lea     rax, [rsp+250h+var_230]
0x1800807aa  mov     [rsp+250h+var_200], rax
0x1800807af  mov     [rsp+250h+var_208], 4
0x1800807b8  mov     [rsp+250h+var_230], r12b
0x1800807bd  mov     [rsp+250h+var_1F8], 1
0x1800807c6  cmp     [r8+10h], r13d
0x1800807ca  jbe     short loc_1800807E4
0x1800807cc  mov     edx, r14d
0x1800807cf  inc     r14d
0x1800807d2  mov     rax, [r8+rdx*8+18h]
0x1800807d7  mov     ecx, [rax+8]
0x1800807da  mov     [rbp+rdx*4+150h+var_130], ecx
0x1800807de  cmp     r14d, [r8+10h]
0x1800807e2  jb      short loc_1800807CC
0x1800807e4  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x1800807eb  lea     rax, [rbp+150h+var_130]
0x1800807ef  mov     qword ptr [rsp+250h+var_1F0], rax
0x1800807f4  lea     rdx, EventD3D11CommandBufferSubmission; ")"
0x1800807fb  mov     eax, r12d
0x1800807fe  mov     [rbp+150h+var_1B0], r9
0x180080802  shl     eax, 2
0x180080805  mov     dword ptr [rsp+250h+var_1E8], eax
0x180080809  lea     rax, [r8+26Ch]
0x180080810  mov     [rbp+150h+var_1D0], rax
0x180080814  mov     rax, [r8+288h]
0x18008081b  mov     [rbp+150h+var_170], rax
0x18008081f  mov     eax, [r9]
0x180080822  lea     r9, [rsp+250h+var_220]
0x180080827  shl     eax, 2
0x18008082a  mov     [rbp+150h+var_168], eax
0x18008082d  mov     rax, [r8+290h]
0x180080834  mov     [rbp+150h+var_160], rax
0x180080838  mov     eax, [r10]
0x18008083b  shl     eax, 2
0x18008083e  mov     [rbp+150h+var_158], eax
0x180080841  mov     rax, [r8+298h]
0x180080848  mov     [rbp+150h+var_150], rax
0x18008084c  mov     eax, [r11]
0x18008084f  shl     eax, 2
0x180080852  mov     [rbp+150h+var_148], eax
0x180080855  mov     rax, [r8+2A0h]
0x18008085c  mov     r8d, 0Fh
0x180080862  mov     [rbp+150h+var_140], rax
0x180080866  mov     eax, [rbx]
0x180080868  shl     eax, 2
0x18008086b  mov     [rbp+150h+var_138], eax
0x18008086e  mov     dword ptr [rsp+250h+var_1E8+4], r13d
0x180080873  mov     [rsp+250h+var_1E0], rsi
0x180080878  mov     [rsp+250h+var_1D8], 4
0x180080881  mov     [rbp+150h+var_1C8], 4
0x180080889  mov     [rbp+150h+var_1C0], rdi
0x18008088d  mov     [rbp+150h+var_1B8], 4
0x180080895  mov     [rbp+150h+var_1A8], 4
0x18008089d  mov     [rbp+150h+var_1A0], r10
0x1800808a1  mov     [rbp+150h+var_198], 4
0x1800808a9  mov     [rbp+150h+var_190], r11
0x1800808ad  mov     [rbp+150h+var_188], 4
0x1800808b5  mov     [rbp+150h+var_180], rbx
0x1800808b9  mov     [rbp+150h+var_178], 4
0x1800808c1  mov     [rbp+150h+var_164], r13d
0x1800808c5  mov     [rbp+150h+var_154], r13d
0x1800808c9  mov     [rbp+150h+var_144], r13d
0x1800808cd  mov     [rbp+150h+var_134], r13d
0x1800808d1  call    cs:__imp_EtwEventWrite
0x1800808d7  xor     eax, eax
0x1800808d9  mov     rcx, [rbp+150h+var_30]
0x1800808e0  xor     rcx, rsp; StackCookie
0x1800808e3  call    __security_check_cookie
0x1800808e8  lea     r11, [rsp+250h+var_20]
0x1800808f0  mov     rbx, [r11+30h]
0x1800808f4  mov     rsi, [r11+40h]
0x1800808f8  mov     rsp, r11
0x1800808fb  pop     r14
0x1800808fd  pop     r13
0x1800808ff  pop     r12
0x180080901  pop     rdi
0x180080902  pop     rbp
0x180080903  retn
0x180080904  cmp     edx, 1
0x180080907  jz      short loc_180080910
0x180080909  mov     eax, 80070057h
0x18008090e  jmp     short loc_1800808D9
0x180080910  lea     rdi, [r8+270h]
0x180080917  cmp     [rdi], r13d
0x18008091a  jnz     short loc_180080909
0x18008091c  lea     r9, [r8+274h]
0x180080923  cmp     [r9], r13d
0x180080926  jnz     short loc_180080909
0x180080928  lea     r10, [r8+278h]
0x18008092f  cmp     [r10], r13d
0x180080932  jnz     short loc_180080909
0x180080934  lea     r11, [r8+27Ch]
0x18008093b  cmp     [r11], r13d
0x18008093e  jnz     short loc_180080909
0x180080940  lea     rbx, [r8+280h]
0x180080947  cmp     [rbx], r13d
0x18008094a  jnz     short loc_180080909
0x18008094c  jmp     loc_18008077F
```
