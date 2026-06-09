# CMsftDiscFormat2Data::DetermineDvdPlusRWState(CMsftDiscInformation *,_IMAPI_FORMAT2_DATA_MEDIA_STATE *)

- ea: `0x180017d94`
- end: `0x180018088`
- name: `?DetermineDvdPlusRWState@CMsftDiscFormat2Data@@AEAAJPEAVCMsftDiscInformation@@PEAW4_IMAPI_FORMAT2_DATA_MEDIA_STATE@@@Z`
- size: `756`
- prototype: `__int64 __fastcall(CMsftDiscFormat2Data *__hidden this, struct CMsftDiscInformation *, enum _IMAPI_FORMAT2_DATA_MEDIA_STATE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180009640`

## callees

- `0x1800140f4`
- `0x180014134`
- `0x180016778`
- `0x180017d94`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001806c`
- `ole32!CoTaskMemFree` at `0x18001806c`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2Data::DetermineDvdPlusRWState(
        CMsftDiscFormat2Data *this,
        struct CMsftDiscInformation *a2,
        enum _IMAPI_FORMAT2_DATA_MEDIA_STATE *a3)
{
  __int64 v3; // rcx
  int v5; // esi
  enum _IMAPI_FORMAT2_DATA_MEDIA_STATE *v6; // r15
  int v7; // eax
  unsigned int v8; // ebp
  PVOID *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  int v13; // [rsp+60h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+20h] BYREF

  v3 = *((_QWORD *)this + 27);
  pv = 0;
  v13 = 0;
  v5 = 1;
  *a3 = IMAPI_FORMAT2_DATA_MEDIA_STATE_UNKNOWN;
  v6 = a3;
  LOBYTE(a3) = 1;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, enum _IMAPI_FORMAT2_DATA_MEDIA_STATE *, LPVOID *, int *))(*(_QWORD *)v3 + 96LL))(
         v3,
         40,
         a3,
         &pv,
         &v13);
  v8 = v7;
  switch ( v7 )
  {
    case -1062600182:
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
      {
        v10 = 230;
LABEL_16:
        WPP_SF_(v9[37], v10, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
        v9 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_17;
      }
      goto LABEL_17;
    case -1062600181:
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
      {
        v10 = 231;
        goto LABEL_16;
      }
LABEL_17:
      v8 = 0;
      v11 = (*(unsigned __int8 *)(*(_QWORD *)a2 + 2LL) >> 2) & 3;
      if ( (*(_BYTE *)(*(_QWORD *)a2 + 2LL) & 3) != 0 )
      {
        if ( v11 )
        {
          if ( (*(_BYTE *)(*(_QWORD *)a2 + 7LL) & 3) != 0 )
          {
            if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 308) & 4) != 0 && *((_BYTE *)v9 + 305) >= 4u )
              WPP_SF_(v9[37], 238, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
          }
          else
          {
            if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 308) & 4) != 0 && *((_BYTE *)v9 + 305) >= 2u )
              WPP_SF_d(v9[37], 237, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, 0);
            v5 = 0x8000;
          }
          goto LABEL_50;
        }
      }
      else if ( !v11 )
      {
        if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 308) & 4) != 0 && *((_BYTE *)v9 + 305) >= 4u )
          WPP_SF_(v9[37], 235, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
        v5 = 2;
LABEL_50:
        *v6 = v5;
        goto LABEL_51;
      }
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 308) & 4) != 0 && *((_BYTE *)v9 + 305) >= 2u )
        WPP_SF_Dd(
          v9[37],
          236,
          &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
          *(_BYTE *)(*(_QWORD *)a2 + 2LL) & 3,
          (*(unsigned __int8 *)(*(_QWORD *)a2 + 2LL) >> 2) & 3);
      v5 = 1024;
      goto LABEL_50;
    case -1062600180:
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
      {
        v10 = 232;
        goto LABEL_16;
      }
      goto LABEL_17;
  }
  if ( v7 >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 234, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
    }
    v5 = 2048;
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 37),
      233,
      &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
      (unsigned int)v7);
  }
LABEL_51:
  CoTaskMemFree(pv);
  return v8;
}

```

## disassembly

```asm
0x180017d94  mov     r11, rsp
0x180017d97  mov     [r11+8], rbp
0x180017d9b  mov     [r11+10h], rsi
0x180017d9f  push    rdi
0x180017da0  push    r14
0x180017da2  push    r15
0x180017da4  sub     rsp, 30h
0x180017da8  mov     rcx, [rcx+0D8h]
0x180017daf  lea     r9, [r11+20h]
0x180017db3  mov     r14, rdx
0x180017db6  mov     qword ptr [r11+20h], 0
0x180017dbe  lea     rdx, [r11+18h]
0x180017dc2  mov     [rsp+48h+arg_10], 0
0x180017dca  mov     esi, 1
0x180017dcf  mov     dword ptr [r8], 0
0x180017dd6  mov     rax, [rcx]
0x180017dd9  mov     r15, r8
0x180017ddc  mov     [r11-28h], rdx
0x180017de0  mov     r8b, sil
0x180017de3  lea     edx, [rsi+27h]
0x180017de6  mov     rax, [rax+60h]
0x180017dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017def  mov     ebp, eax
0x180017df1  cmp     eax, 0C0AA020Ah
0x180017df6  jnz     short loc_180017E30
0x180017df8  mov     rcx, cs:WPP_GLOBAL_Control
0x180017dff  lea     rdi, WPP_GLOBAL_Control
0x180017e06  cmp     rcx, rdi
0x180017e09  jz      loc_180017EB2
0x180017e0f  test    byte ptr [rcx+134h], 4
0x180017e16  jz      loc_180017EB2
0x180017e1c  cmp     byte ptr [rcx+131h], 4
0x180017e23  jb      loc_180017EB2
0x180017e29  mov     edx, 0E6h
0x180017e2e  jmp     short loc_180017E98
0x180017e30  cmp     eax, 0C0AA020Bh
0x180017e35  jnz     short loc_180017E63
0x180017e37  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e3e  lea     rdi, WPP_GLOBAL_Control
0x180017e45  cmp     rcx, rdi
0x180017e48  jz      short loc_180017EB2
0x180017e4a  test    byte ptr [rcx+134h], 4
0x180017e51  jz      short loc_180017EB2
0x180017e53  cmp     byte ptr [rcx+131h], 4
0x180017e5a  jb      short loc_180017EB2
0x180017e5c  mov     edx, 0E7h
0x180017e61  jmp     short loc_180017E98
0x180017e63  cmp     eax, 0C0AA020Ch
0x180017e68  jnz     loc_180017FDC
0x180017e6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e75  lea     rdi, WPP_GLOBAL_Control
0x180017e7c  cmp     rcx, rdi
0x180017e7f  jz      short loc_180017EB2
0x180017e81  test    byte ptr [rcx+134h], 4
0x180017e88  jz      short loc_180017EB2
0x180017e8a  cmp     byte ptr [rcx+131h], 4
0x180017e91  jb      short loc_180017EB2
0x180017e93  mov     edx, 0E8h
0x180017e98  mov     rcx, [rcx+128h]
0x180017e9f  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180017ea6  call    WPP_SF_
0x180017eab  mov     rcx, cs:WPP_GLOBAL_Control
0x180017eb2  mov     rdx, [r14]
0x180017eb5  xor     ebp, ebp
0x180017eb7  movzx   eax, byte ptr [rdx+2]
0x180017ebb  mov     r9d, eax
0x180017ebe  shr     eax, 2
0x180017ec1  and     eax, 3
0x180017ec4  and     r9d, 3
0x180017ec8  jnz     short loc_180017F0B
0x180017eca  test    eax, eax
0x180017ecc  jnz     loc_180017F9A
0x180017ed2  cmp     rcx, rdi
0x180017ed5  jz      short loc_180017F01
0x180017ed7  test    byte ptr [rcx+134h], 4
0x180017ede  jz      short loc_180017F01
0x180017ee0  cmp     byte ptr [rcx+131h], 4
0x180017ee7  jb      short loc_180017F01
0x180017ee9  mov     rcx, [rcx+128h]
0x180017ef0  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180017ef7  mov     edx, 0EBh
0x180017efc  call    WPP_SF_
0x180017f01  mov     esi, 2
0x180017f06  jmp     loc_180018064
0x180017f0b  test    eax, eax
0x180017f0d  jz      loc_180017F9A
0x180017f13  test    byte ptr [rdx+7], 3
0x180017f17  jnz     short loc_180017F5A
0x180017f19  cmp     rcx, rdi
0x180017f1c  jz      short loc_180017F50
0x180017f1e  test    byte ptr [rcx+134h], 4
0x180017f25  jz      short loc_180017F50
0x180017f27  mov     esi, 2
0x180017f2c  cmp     [rcx+131h], sil
0x180017f33  jb      short loc_180017F50
0x180017f35  mov     rcx, [rcx+128h]
0x180017f3c  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180017f43  mov     edx, 0EDh
0x180017f48  xor     r9d, r9d
0x180017f4b  call    WPP_SF_d
0x180017f50  mov     esi, 8000h
0x180017f55  jmp     loc_180018064
0x180017f5a  cmp     rcx, rdi
0x180017f5d  jz      loc_180018064
0x180017f63  test    byte ptr [rcx+134h], 4
0x180017f6a  jz      loc_180018064
0x180017f70  cmp     byte ptr [rcx+131h], 4
0x180017f77  jb      loc_180018064
0x180017f7d  mov     rcx, [rcx+128h]
0x180017f84  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180017f8b  mov     edx, 0EEh
0x180017f90  call    WPP_SF_
0x180017f95  jmp     loc_180018064
0x180017f9a  cmp     rcx, rdi
0x180017f9d  jz      short loc_180017FD2
0x180017f9f  test    byte ptr [rcx+134h], 4
0x180017fa6  jz      short loc_180017FD2
0x180017fa8  mov     esi, 2
0x180017fad  cmp     [rcx+131h], sil
0x180017fb4  jb      short loc_180017FD2
0x180017fb6  mov     rcx, [rcx+128h]
0x180017fbd  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180017fc4  mov     edx, 0ECh
0x180017fc9  mov     [rsp+48h+var_28], eax
0x180017fcd  call    WPP_SF_Dd
0x180017fd2  mov     esi, 400h
0x180017fd7  jmp     loc_180018064
0x180017fdc  test    eax, eax
0x180017fde  jns     short loc_180018022
0x180017fe0  mov     rcx, cs:WPP_GLOBAL_Control
0x180017fe7  lea     rdi, WPP_GLOBAL_Control
0x180017fee  cmp     rcx, rdi
0x180017ff1  jz      short loc_180018067
0x180017ff3  test    byte ptr [rcx+134h], 4
0x180017ffa  jz      short loc_180018067
0x180017ffc  cmp     byte ptr [rcx+131h], 3
0x180018003  jb      short loc_180018067
0x180018005  mov     rcx, [rcx+128h]
0x18001800c  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180018013  mov     edx, 0E9h
0x180018018  mov     r9d, eax
0x18001801b  call    WPP_SF_d
0x180018020  jmp     short loc_180018067
0x180018022  mov     rcx, cs:WPP_GLOBAL_Control
0x180018029  lea     rdi, WPP_GLOBAL_Control
0x180018030  cmp     rcx, rdi
0x180018033  jz      short loc_18001805F
0x180018035  test    byte ptr [rcx+134h], 4
0x18001803c  jz      short loc_18001805F
0x18001803e  cmp     byte ptr [rcx+131h], 4
0x180018045  jb      short loc_18001805F
0x180018047  mov     rcx, [rcx+128h]
0x18001804e  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180018055  mov     edx, 0EAh
0x18001805a  call    WPP_SF_
0x18001805f  mov     esi, 800h
0x180018064  mov     [r15], esi
0x180018067  mov     rcx, [rsp+48h+pv]; pv
0x18001806c  call    cs:__imp_CoTaskMemFree
0x180018072  mov     rsi, [rsp+48h+arg_8]
0x180018077  mov     eax, ebp
0x180018079  mov     rbp, [rsp+48h+arg_0]
0x18001807e  add     rsp, 30h
0x180018082  pop     r15
0x180018084  pop     r14
0x180018086  pop     rdi
0x180018087  retn
```
