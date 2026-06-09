# MidlFreeDasDeviceCreationInfo(_DAS_SW_DEVICE_CREATE_INFO *)

- ea: `0x140019f38`
- end: `0x14001a05f`
- name: `?MidlFreeDasDeviceCreationInfo@@YAXPEAU_DAS_SW_DEVICE_CREATE_INFO@@@Z`
- size: `295`
- prototype: `void __fastcall(struct _DAS_SW_DEVICE_CREATE_INFO *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14000deb0`
- `0x14000ef44`
- `0x14000f83c`
- `0x140019b20`
- `0x14001a208`

## callees

- `0x140009090`
- `0x140019f38`

## pseudocode

```c
void __fastcall MidlFreeDasDeviceCreationInfo(struct _DAS_SW_DEVICE_CREATE_INFO *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  _QWORD *v6; // rdi
  unsigned int v7; // r14d
  __int64 i; // rsi
  void *v9; // rcx
  _QWORD *v10; // rdi
  unsigned int v11; // r14d
  __int64 j; // rsi
  void *v13; // rcx
  void *v14; // rcx

  if ( a1 )
  {
    v2 = (void *)*((_QWORD *)a1 + 8);
    if ( v2 )
    {
      MIDL_user_free(v2);
      *((_QWORD *)a1 + 8) = 0;
    }
    v3 = (void *)*((_QWORD *)a1 + 6);
    if ( v3 )
    {
      MIDL_user_free(v3);
      *((_QWORD *)a1 + 6) = 0;
    }
    v4 = (void *)*((_QWORD *)a1 + 9);
    if ( v4 )
    {
      MIDL_user_free(v4);
      *((_QWORD *)a1 + 9) = 0;
    }
    v5 = (void *)*((_QWORD *)a1 + 1);
    if ( v5 )
    {
      MIDL_user_free(v5);
      *((_QWORD *)a1 + 1) = 0;
    }
    v6 = (_QWORD *)*((_QWORD *)a1 + 5);
    if ( v6 )
    {
      v7 = *((_DWORD *)a1 + 8);
      for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
      {
        v9 = (void *)v6[i];
        if ( v9 )
        {
          MIDL_user_free(v9);
          v6[i] = 0;
        }
      }
      MIDL_user_free(v6);
      *((_QWORD *)a1 + 5) = 0;
      *((_DWORD *)a1 + 8) = 0;
    }
    v10 = (_QWORD *)*((_QWORD *)a1 + 3);
    if ( v10 )
    {
      v11 = *((_DWORD *)a1 + 4);
      for ( j = 0; (unsigned int)j < v11; j = (unsigned int)(j + 1) )
      {
        v13 = (void *)v10[j];
        if ( v13 )
        {
          MIDL_user_free(v13);
          v10[j] = 0;
        }
      }
      MIDL_user_free(v10);
      *((_QWORD *)a1 + 3) = 0;
      *((_DWORD *)a1 + 4) = 0;
    }
    v14 = (void *)*((_QWORD *)a1 + 10);
    if ( v14 )
    {
      MIDL_user_free(v14);
      *((_QWORD *)a1 + 10) = 0;
    }
    MIDL_user_free(a1);
  }
}

```

## disassembly

```asm
0x140019f38  test    rcx, rcx
0x140019f3b  jz      locret_14001A05E
0x140019f41  push    rbx
0x140019f42  push    rbp
0x140019f43  push    rsi
0x140019f44  push    rdi
0x140019f45  push    r14
0x140019f47  sub     rsp, 20h
0x140019f4b  mov     rbx, rcx
0x140019f4e  mov     rcx, [rcx+40h]; void *
0x140019f52  test    rcx, rcx
0x140019f55  jz      short loc_140019F64
0x140019f57  call    MIDL_user_free
0x140019f5c  mov     qword ptr [rbx+40h], 0
0x140019f64  mov     rcx, [rbx+30h]; void *
0x140019f68  test    rcx, rcx
0x140019f6b  jz      short loc_140019F7A
0x140019f6d  call    MIDL_user_free
0x140019f72  mov     qword ptr [rbx+30h], 0
0x140019f7a  mov     rcx, [rbx+48h]; void *
0x140019f7e  test    rcx, rcx
0x140019f81  jz      short loc_140019F90
0x140019f83  call    MIDL_user_free
0x140019f88  mov     qword ptr [rbx+48h], 0
0x140019f90  mov     rcx, [rbx+8]; void *
0x140019f94  test    rcx, rcx
0x140019f97  jz      short loc_140019FA6
0x140019f99  call    MIDL_user_free
0x140019f9e  mov     qword ptr [rbx+8], 0
0x140019fa6  mov     rdi, [rbx+28h]
0x140019faa  test    rdi, rdi
0x140019fad  jz      short loc_140019FEE
0x140019faf  mov     r14d, [rbx+20h]
0x140019fb3  xor     esi, esi
0x140019fb5  test    r14d, r14d
0x140019fb8  jz      short loc_140019FD7
0x140019fba  mov     rcx, [rdi+rsi*8]; void *
0x140019fbe  test    rcx, rcx
0x140019fc1  jz      short loc_140019FD0
0x140019fc3  call    MIDL_user_free
0x140019fc8  mov     qword ptr [rdi+rsi*8], 0
0x140019fd0  inc     esi
0x140019fd2  cmp     esi, r14d
0x140019fd5  jb      short loc_140019FBA
0x140019fd7  mov     rcx, rdi; void *
0x140019fda  call    MIDL_user_free
0x140019fdf  mov     qword ptr [rbx+28h], 0
0x140019fe7  mov     dword ptr [rbx+20h], 0
0x140019fee  mov     rdi, [rbx+18h]
0x140019ff2  test    rdi, rdi
0x140019ff5  jz      short loc_14001A036
0x140019ff7  mov     r14d, [rbx+10h]
0x140019ffb  xor     esi, esi
0x140019ffd  test    r14d, r14d
0x14001a000  jz      short loc_14001A01F
0x14001a002  mov     rcx, [rdi+rsi*8]; void *
0x14001a006  test    rcx, rcx
0x14001a009  jz      short loc_14001A018
0x14001a00b  call    MIDL_user_free
0x14001a010  mov     qword ptr [rdi+rsi*8], 0
0x14001a018  inc     esi
0x14001a01a  cmp     esi, r14d
0x14001a01d  jb      short loc_14001A002
0x14001a01f  mov     rcx, rdi; void *
0x14001a022  call    MIDL_user_free
0x14001a027  mov     qword ptr [rbx+18h], 0
0x14001a02f  mov     dword ptr [rbx+10h], 0
0x14001a036  mov     rcx, [rbx+50h]; void *
0x14001a03a  test    rcx, rcx
0x14001a03d  jz      short loc_14001A04C
0x14001a03f  call    MIDL_user_free
0x14001a044  mov     qword ptr [rbx+50h], 0
0x14001a04c  mov     rcx, rbx; void *
0x14001a04f  call    MIDL_user_free
0x14001a054  add     rsp, 20h
0x14001a058  pop     r14
0x14001a05a  pop     rdi
0x14001a05b  pop     rsi
0x14001a05c  pop     rbp
0x14001a05d  pop     rbx
0x14001a05e  retn
```
