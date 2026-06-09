# MQpQueueFormatToFormatName(QUEUE_FORMAT const *,wchar_t *,ulong,ulong *,bool)

- ea: `0x140002b74`
- end: `0x140002d1c`
- name: `?MQpQueueFormatToFormatName@@YAJPEBUQUEUE_FORMAT@@PEA_WKPEAK_N@Z`
- size: `424`
- prototype: `__int64 __usercall@<rax>(const struct QUEUE_FORMAT *@<rcx>, wchar_t *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, bool)`
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x140002650`
- `0x1400140a0`
- `0x14001bd4c`
- `0x14001e0c0`
- `0x14001efc0`

## callees

- `0x1400026e0`
- `0x140002790`
- `0x1400028a0`
- `0x140002950`
- `0x140002a0c`
- `0x140002ac4`
- `0x140002b74`
- `0x140002f2c`

## pseudocode

```c
__int64 __fastcall MQpQueueFormatToFormatName(
        const struct QUEUE_FORMAT *a1,
        wchar_t *a2,
        unsigned int a3,
        unsigned int *a4,
        bool a5)
{
  int v9; // ebx
  const wchar_t *v10; // r10
  __int64 v11; // rax
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  __int64 v19; // rax
  unsigned int v20; // ebx
  _DWORD v21[6]; // [rsp+30h] [rbp-40h]
  _QWORD v22[5]; // [rsp+48h] [rbp-28h]

  if ( (a3 & 0x40000000) != 0 )
    return 3222143007LL;
  v21[0] = 0;
  v22[0] = &qword_140027730;
  v22[1] = L";JOURNAL";
  v22[2] = L";DEADLETTER";
  v22[3] = L";DEADXACT";
  v22[4] = L";XACTONLY";
  v21[3] = 9;
  v21[4] = 9;
  v21[1] = 8;
  v21[2] = 11;
  if ( a5 )
  {
    v9 = 1;
    v10 = L",";
  }
  else
  {
    v11 = *((_BYTE *)a1 + 1) & 0xF;
    v10 = (const wchar_t *)v22[v11];
    v9 = v21[v11];
  }
  v12 = *(unsigned __int8 *)a1 - 1;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            v17 = v16 - 1;
            if ( v17 )
            {
              if ( v17 != 1 )
              {
                *a4 = 0;
                return 3221225485LL;
              }
              LODWORD(v19) = MQpMulticastToFormatName(a1, a3, a2);
            }
            else
            {
              LODWORD(v19) = MQpDlToFormatName(a1, a3, a2);
            }
          }
          else
          {
            LODWORD(v19) = MQpConnectorToFormatName(a1, v10, a3, a2);
          }
        }
        else
        {
          LODWORD(v19) = MQpMachineToFormatName(a1, v10, a3, a2);
        }
      }
      else
      {
        StringCchPrintfW(a2, a3, L"DIRECT=%s%s", *((_QWORD *)a1 + 1), v10);
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * v19) );
        v9 += 8;
      }
    }
    else
    {
      LODWORD(v19) = MQpPrivateToFormatName(a1, v10, a3, a2);
    }
  }
  else
  {
    LODWORD(v19) = MQpPublicToFormatName(a1, v10, a3, a2);
  }
  v20 = v19 + v9;
  *a4 = v20;
  if ( a3 < v20 )
  {
    if ( a3 )
      a2[a3 - 1] = 0;
    return 3222143007LL;
  }
  return 0;
}

```

## disassembly

```asm
0x140002b74  push    rbp
0x140002b76  push    rbx
0x140002b77  push    rsi
0x140002b78  push    rdi
0x140002b79  push    r12
0x140002b7b  push    r14
0x140002b7d  push    r15
0x140002b7f  mov     rbp, rsp
0x140002b82  sub     rsp, 70h
0x140002b86  mov     edi, r8d
0x140002b89  xor     r12d, r12d
0x140002b8c  mov     r15, r9
0x140002b8f  mov     r14, rdx
0x140002b92  mov     rsi, rcx
0x140002b95  lea     eax, [rdi+rdi]
0x140002b98  test    eax, eax
0x140002b9a  js      loc_140002D03
0x140002ba0  lea     rax, qword_140027730
0x140002ba7  mov     [rbp+var_40], r12d
0x140002bab  mov     [rbp+var_28], rax
0x140002baf  lea     rax, aJournal; ";JOURNAL"
0x140002bb6  mov     [rbp+var_20], rax
0x140002bba  lea     rax, aDeadletter; ";DEADLETTER"
0x140002bc1  mov     [rbp+var_18], rax
0x140002bc5  lea     rax, aDeadxact; ";DEADXACT"
0x140002bcc  mov     [rbp+var_10], rax
0x140002bd0  lea     rax, aXactonly; ";XACTONLY"
0x140002bd7  mov     [rbp+var_8], rax
0x140002bdb  lea     eax, [r12+9]
0x140002be0  mov     [rbp+var_34], eax
0x140002be3  mov     [rbp+var_30], eax
0x140002be6  mov     [rbp+var_3C], 8
0x140002bed  mov     [rbp+var_38], 0Bh
0x140002bf4  cmp     [rbp+arg_20], r12b
0x140002bf8  jz      short loc_140002C06
0x140002bfa  lea     ebx, [rax-8]
0x140002bfd  lea     r10, asc_140027ADC; ","
0x140002c04  jmp     short loc_140002C16
0x140002c06  movzx   eax, byte ptr [rcx+1]
0x140002c0a  and     eax, 0Fh
0x140002c0d  mov     r10, [rbp+rax*8+var_28]
0x140002c12  mov     ebx, [rbp+rax*4+var_40]
0x140002c16  movzx   ecx, byte ptr [rcx]
0x140002c19  sub     ecx, 1
0x140002c1c  jz      loc_140002CDD
0x140002c22  sub     ecx, 1
0x140002c25  jz      loc_140002CCA
0x140002c2b  sub     ecx, 1
0x140002c2e  jz      short loc_140002C98
0x140002c30  sub     ecx, 1
0x140002c33  jz      short loc_140002C85
0x140002c35  sub     ecx, 1
0x140002c38  jz      short loc_140002C72
0x140002c3a  sub     ecx, 1
0x140002c3d  jz      short loc_140002C63
0x140002c3f  cmp     ecx, 1
0x140002c42  jz      short loc_140002C51
0x140002c44  mov     [r9], r12d
0x140002c47  mov     eax, 0C000000Dh
0x140002c4c  jmp     loc_140002D08
0x140002c51  mov     r8, r14; wchar_t *
0x140002c54  mov     edx, edi; unsigned int
0x140002c56  mov     rcx, rsi; struct QUEUE_FORMAT *
0x140002c59  call    ?MQpMulticastToFormatName@@YAKPEBUQUEUE_FORMAT@@KPEA_W@Z; MQpMulticastToFormatName(QUEUE_FORMAT const *,ulong,wchar_t *)
0x140002c5e  jmp     loc_140002CEE
0x140002c63  mov     r8, r14; wchar_t *
0x140002c66  mov     edx, edi; unsigned int
0x140002c68  mov     rcx, rsi; struct QUEUE_FORMAT *
0x140002c6b  call    ?MQpDlToFormatName@@YAKPEBUQUEUE_FORMAT@@KPEA_W@Z; MQpDlToFormatName(QUEUE_FORMAT const *,ulong,wchar_t *)
0x140002c70  jmp     short loc_140002CEE
0x140002c72  mov     r9, r14; wchar_t *
0x140002c75  mov     r8d, edi; unsigned int
0x140002c78  mov     rdx, r10; wchar_t *
0x140002c7b  mov     rcx, rsi; struct QUEUE_FORMAT *
0x140002c7e  call    ?MQpConnectorToFormatName@@YAKPEBUQUEUE_FORMAT@@PEB_WKPEA_W@Z; MQpConnectorToFormatName(QUEUE_FORMAT const *,wchar_t const *,ulong,wchar_t *)
0x140002c83  jmp     short loc_140002CEE
0x140002c85  mov     r9, r14; wchar_t *
0x140002c88  mov     r8d, edi; unsigned int
0x140002c8b  mov     rdx, r10; wchar_t *
0x140002c8e  mov     rcx, rsi; struct QUEUE_FORMAT *
0x140002c91  call    ?MQpMachineToFormatName@@YAKPEBUQUEUE_FORMAT@@PEB_WKPEA_W@Z; MQpMachineToFormatName(QUEUE_FORMAT const *,wchar_t const *,ulong,wchar_t *)
0x140002c96  jmp     short loc_140002CEE
0x140002c98  mov     r9, [rsi+8]
0x140002c9c  lea     r8, aDirectSS; "DIRECT=%s%s"
0x140002ca3  mov     rdx, rdi; unsigned __int64
0x140002ca6  mov     [rsp+70h+var_50], r10
0x140002cab  mov     rcx, r14; wchar_t *
0x140002cae  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140002cb3  mov     rcx, [rsi+8]
0x140002cb7  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002cbb  inc     rax
0x140002cbe  cmp     [rcx+rax*2], r12w
0x140002cc3  jnz     short loc_140002CBB
0x140002cc5  add     ebx, 8
0x140002cc8  jmp     short loc_140002CEE
0x140002cca  mov     r9, r14; wchar_t *
0x140002ccd  mov     r8d, edi; unsigned int
0x140002cd0  mov     rdx, r10; wchar_t *
0x140002cd3  mov     rcx, rsi; struct QUEUE_FORMAT *
0x140002cd6  call    ?MQpPrivateToFormatName@@YAKPEBUQUEUE_FORMAT@@PEB_WKPEA_W@Z; MQpPrivateToFormatName(QUEUE_FORMAT const *,wchar_t const *,ulong,wchar_t *)
0x140002cdb  jmp     short loc_140002CEE
0x140002cdd  mov     r9, r14; wchar_t *
0x140002ce0  mov     r8d, edi; unsigned int
0x140002ce3  mov     rdx, r10; wchar_t *
0x140002ce6  mov     rcx, rsi; struct QUEUE_FORMAT *
0x140002ce9  call    ?MQpPublicToFormatName@@YAKPEBUQUEUE_FORMAT@@PEB_WKPEA_W@Z; MQpPublicToFormatName(QUEUE_FORMAT const *,wchar_t const *,ulong,wchar_t *)
0x140002cee  add     ebx, eax
0x140002cf0  mov     [r15], ebx
0x140002cf3  cmp     edi, ebx
0x140002cf5  jnb     short loc_140002D18
0x140002cf7  test    edi, edi
0x140002cf9  jz      short loc_140002D03
0x140002cfb  lea     eax, [rdi-1]
0x140002cfe  mov     [r14+rax*2], r12w
0x140002d03  mov     eax, 0C00E001Fh
0x140002d08  add     rsp, 70h
0x140002d0c  pop     r15
0x140002d0e  pop     r14
0x140002d10  pop     r12
0x140002d12  pop     rdi
0x140002d13  pop     rsi
0x140002d14  pop     rbx
0x140002d15  pop     rbp
0x140002d16  retn
0x140002d18  xor     eax, eax
0x140002d1a  jmp     short loc_140002D08
```
