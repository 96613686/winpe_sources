# NetpCompareFtinfoEntrySid2

- ea: `0x180038150`
- end: `0x180038219`
- name: `NetpCompareFtinfoEntrySid2`
- size: `201`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180038150`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800381c4`
- `ntdll!RtlLengthSid` at `0x1800381cf`
- `ntdll!RtlLengthSid` at `0x1800381c4`
- `ntdll!RtlLengthSid` at `0x1800381cf`

## pseudocode

```c
__int64 __fastcall NetpCompareFtinfoEntrySid2(__int64 *a1, __int64 *a2)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v6; // rsi
  unsigned __int8 *v7; // rbx
  ULONG v9; // edi
  ULONG v10; // eax
  __int64 v11; // rdx
  int v12; // r8d
  int v13; // r9d

  v2 = *a1;
  v3 = *a2;
  if ( *(_DWORD *)(*a1 + 4) != 2 )
  {
    if ( *(_DWORD *)(v3 + 4) == 2 )
      return 1;
    v4 = 0x6DB6DB6DB6DB6DB7LL * ((v2 - v3) >> 3);
    if ( v4 >= 0 )
      return v4 > 0;
    return 0xFFFFFFFFLL;
  }
  if ( *(_DWORD *)(v3 + 4) != 2 )
    return 0xFFFFFFFFLL;
  v6 = *(_QWORD *)(v2 + 16);
  v7 = *(unsigned __int8 **)(v3 + 16);
  if ( v6 )
  {
    if ( v7 )
    {
      v9 = RtlLengthSid(*(PSID *)(v2 + 16));
      v10 = RtlLengthSid(v7);
      if ( v9 == v10 )
      {
        v11 = 0;
        if ( v9 )
        {
          while ( 1 )
          {
            v12 = *(unsigned __int8 *)(v11 + v6);
            v13 = v7[v11];
            if ( (_BYTE)v12 != (_BYTE)v13 )
              break;
            v11 = (unsigned int)(v11 + 1);
            if ( (unsigned int)v11 >= v9 )
              return 0;
          }
          return (unsigned int)(v12 - v13);
        }
        else
        {
          return 0;
        }
      }
      else
      {
        return v9 - v10;
      }
    }
    else
    {
      return 1;
    }
  }
  else
  {
    return (unsigned int)-(v7 != 0);
  }
}

```

## disassembly

```asm
0x180038150  mov     [rsp+arg_0], rbx
0x180038155  mov     [rsp+arg_8], rsi
0x18003815a  push    rdi
0x18003815b  sub     rsp, 20h
0x18003815f  mov     rax, [rcx]
0x180038162  mov     rbx, [rdx]
0x180038165  cmp     dword ptr [rax+4], 2
0x180038169  jz      short loc_180038198
0x18003816b  cmp     dword ptr [rbx+4], 2
0x18003816f  jz      short loc_180038191
0x180038171  sub     rax, rbx
0x180038174  mov     rcx, 6DB6DB6DB6DB6DB7h
0x18003817e  sar     rax, 3
0x180038182  imul    rax, rcx
0x180038186  test    rax, rax
0x180038189  js      short loc_18003819E
0x18003818b  jg      short loc_180038191
0x18003818d  xor     eax, eax
0x18003818f  jmp     short loc_180038201
0x180038191  mov     eax, 1
0x180038196  jmp     short loc_180038201
0x180038198  cmp     dword ptr [rbx+4], 2
0x18003819c  jz      short loc_1800381A3
0x18003819e  or      eax, 0FFFFFFFFh
0x1800381a1  jmp     short loc_180038201
0x1800381a3  mov     rsi, [rax+10h]
0x1800381a7  mov     rbx, [rbx+10h]
0x1800381ab  test    rsi, rsi
0x1800381ae  jnz     short loc_1800381B7
0x1800381b0  neg     rbx
0x1800381b3  sbb     ecx, ecx
0x1800381b5  jmp     short loc_1800381FF
0x1800381b7  test    rbx, rbx
0x1800381ba  jnz     short loc_1800381C1
0x1800381bc  lea     ecx, [rbx+1]
0x1800381bf  jmp     short loc_1800381FF
0x1800381c1  mov     rcx, rsi; Sid
0x1800381c4  call    cs:__imp_RtlLengthSid
0x1800381ca  mov     rcx, rbx; Sid
0x1800381cd  mov     edi, eax
0x1800381cf  call    cs:__imp_RtlLengthSid
0x1800381d5  cmp     edi, eax
0x1800381d7  jz      short loc_1800381DF
0x1800381d9  mov     ecx, edi
0x1800381db  sub     ecx, eax
0x1800381dd  jmp     short loc_1800381FF
0x1800381df  xor     edx, edx
0x1800381e1  test    edi, edi
0x1800381e3  jz      short loc_1800381FD
0x1800381e5  lea     ecx, [rdx+1]
0x1800381e8  movzx   r8d, byte ptr [rdx+rsi]
0x1800381ed  movzx   r9d, byte ptr [rdx+rbx]
0x1800381f2  cmp     r8b, r9b
0x1800381f5  jnz     short loc_180038211
0x1800381f7  add     edx, ecx
0x1800381f9  cmp     edx, edi
0x1800381fb  jb      short loc_1800381E8
0x1800381fd  xor     ecx, ecx
0x1800381ff  mov     eax, ecx
0x180038201  mov     rbx, [rsp+28h+arg_0]
0x180038206  mov     rsi, [rsp+28h+arg_8]
0x18003820b  add     rsp, 20h
0x18003820f  pop     rdi
0x180038210  retn
0x180038211  mov     ecx, r8d
0x180038214  sub     ecx, r9d
0x180038217  jmp     short loc_1800381FF
```
