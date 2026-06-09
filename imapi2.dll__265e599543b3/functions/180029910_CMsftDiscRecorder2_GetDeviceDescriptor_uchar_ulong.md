# CMsftDiscRecorder2::GetDeviceDescriptor(uchar * *,ulong *)

- ea: `0x180029910`
- end: `0x180029ac6`
- name: `?GetDeviceDescriptor@CMsftDiscRecorder2@@UEAAJPEAPEAEPEAK@Z`
- size: `438`
- prototype: `__int64 __fastcall(CMsftDiscRecorder2 *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180014134`
- `0x180016778`
- `0x180029910`
- `0x180049832`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800299bb`
- `ole32!CoTaskMemFree` at `0x1800299bb`
- `ole32!CoTaskMemAlloc` at `0x180029a34`
- `ole32!CoTaskMemAlloc` at `0x180029a34`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::GetDeviceDescriptor(
        CMsftDiscRecorder2 *this,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  PVOID *v6; // rcx
  int v7; // ebx
  __int64 v9; // r9
  unsigned __int8 *v10; // rax
  unsigned __int8 *v11; // rsi

  if ( a2 )
  {
    v7 = 0;
    *a2 = 0;
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 81, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = -2147467261;
  }
  if ( a3 )
  {
    *a3 = 0;
    if ( v7 >= 0 )
    {
      v9 = *((unsigned int *)this + 58);
      if ( (v9 & 2) != 0 )
      {
        v10 = (unsigned __int8 *)CoTaskMemAlloc(*(unsigned int *)(*((_QWORD *)this + 18) + 4LL));
        v11 = v10;
        if ( v10 )
        {
          v7 = 0;
          memcpy_0(v10, *((const void **)this + 18), *(unsigned int *)(*((_QWORD *)this + 18) + 4LL));
          *a2 = v11;
          *a3 = *(_DWORD *)(*((_QWORD *)this + 18) + 4LL);
          return (unsigned int)v7;
        }
        v7 = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            84,
            &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
            *(unsigned int *)(*((_QWORD *)this + 18) + 4LL),
            *(_DWORD *)(*((_QWORD *)this + 18) + 4LL));
        }
      }
      else
      {
        v7 = -2147467259;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            83,
            &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
            v9,
            -2147467259);
        }
      }
    }
  }
  else
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 188) & 4) != 0 && *((_BYTE *)v6 + 185) >= 3u )
      WPP_SF_(v6[22], 82, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    v7 = -2147467261;
  }
  CoTaskMemFree(0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180029910  push    rbx
0x180029912  push    rsi
0x180029913  push    rdi
0x180029914  push    r13
0x180029916  push    r14
0x180029918  push    r15
0x18002991a  sub     rsp, 38h
0x18002991e  lea     r13, WPP_GLOBAL_Control
0x180029925  mov     r14, r8
0x180029928  mov     r15, rdx
0x18002992b  mov     rdi, rcx
0x18002992e  mov     esi, 80004003h
0x180029933  test    rdx, rdx
0x180029936  jnz     short loc_180029978
0x180029938  mov     rcx, cs:WPP_GLOBAL_Control
0x18002993f  cmp     rcx, r13
0x180029942  jz      short loc_180029974
0x180029944  test    byte ptr [rcx+0BCh], 4
0x18002994b  jz      short loc_180029974
0x18002994d  cmp     byte ptr [rcx+0B9h], 3
0x180029954  jb      short loc_180029974
0x180029956  mov     rcx, [rcx+0B0h]
0x18002995d  lea     edx, [r15+51h]
0x180029961  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180029968  call    WPP_SF_
0x18002996d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029974  mov     ebx, esi
0x180029976  jmp     short loc_180029984
0x180029978  xor     ebx, ebx
0x18002997a  mov     [rdx], rbx
0x18002997d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029984  test    r14, r14
0x180029987  jnz     short loc_1800299D1
0x180029989  cmp     rcx, r13
0x18002998c  jz      short loc_1800299B7
0x18002998e  test    byte ptr [rcx+0BCh], 4
0x180029995  jz      short loc_1800299B7
0x180029997  cmp     byte ptr [rcx+0B9h], 3
0x18002999e  jb      short loc_1800299B7
0x1800299a0  mov     rcx, [rcx+0B0h]
0x1800299a7  lea     edx, [r14+52h]
0x1800299ab  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x1800299b2  call    WPP_SF_
0x1800299b7  mov     ebx, esi
0x1800299b9  xor     ecx, ecx; pv
0x1800299bb  call    cs:__imp_CoTaskMemFree
0x1800299c1  mov     eax, ebx
0x1800299c3  add     rsp, 38h
0x1800299c7  pop     r15
0x1800299c9  pop     r14
0x1800299cb  pop     r13
0x1800299cd  pop     rdi
0x1800299ce  pop     rsi
0x1800299cf  pop     rbx
0x1800299d0  retn
0x1800299d1  mov     dword ptr [r14], 0
0x1800299d8  test    ebx, ebx
0x1800299da  js      short loc_1800299B9
0x1800299dc  mov     r9d, [rdi+0E8h]
0x1800299e3  test    r9b, 2
0x1800299e7  jnz     short loc_180029A2A
0x1800299e9  mov     ebx, 80004005h
0x1800299ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800299f5  cmp     rcx, r13
0x1800299f8  jz      short loc_1800299B9
0x1800299fa  test    byte ptr [rcx+0BCh], 4
0x180029a01  jz      short loc_1800299B9
0x180029a03  cmp     byte ptr [rcx+0B9h], 3
0x180029a0a  jb      short loc_1800299B9
0x180029a0c  mov     rcx, [rcx+0B0h]
0x180029a13  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180029a1a  mov     edx, 53h ; 'S'
0x180029a1f  mov     [rsp+68h+var_48], ebx
0x180029a23  call    WPP_SF_Dd
0x180029a28  jmp     short loc_1800299B9
0x180029a2a  mov     rax, [rdi+90h]
0x180029a31  mov     ecx, [rax+4]; cb
0x180029a34  call    cs:__imp_CoTaskMemAlloc
0x180029a3a  mov     rsi, rax
0x180029a3d  test    rax, rax
0x180029a40  jnz     short loc_180029A9C
0x180029a42  mov     ebx, 8007000Eh
0x180029a47  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a4e  cmp     rcx, r13
0x180029a51  jz      loc_1800299B9
0x180029a57  test    byte ptr [rcx+0BCh], 4
0x180029a5e  jz      loc_1800299B9
0x180029a64  cmp     byte ptr [rcx+0B9h], 3
0x180029a6b  jb      loc_1800299B9
0x180029a71  mov     rax, [rdi+90h]
0x180029a78  lea     edx, [rsi+54h]
0x180029a7b  mov     rcx, [rcx+0B0h]
0x180029a82  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180029a89  mov     r9d, [rax+4]
0x180029a8d  mov     [rsp+68h+var_48], r9d
0x180029a92  call    WPP_SF_Dd
0x180029a97  jmp     loc_1800299B9
0x180029a9c  mov     rdx, [rdi+90h]; Src
0x180029aa3  xor     ebx, ebx
0x180029aa5  mov     rcx, rsi; void *
0x180029aa8  mov     r8d, [rdx+4]; Size
0x180029aac  call    memcpy_0
0x180029ab1  mov     [r15], rsi
0x180029ab4  mov     rax, [rdi+90h]
0x180029abb  mov     ecx, [rax+4]
0x180029abe  mov     [r14], ecx
0x180029ac1  jmp     loc_1800299C1
```
