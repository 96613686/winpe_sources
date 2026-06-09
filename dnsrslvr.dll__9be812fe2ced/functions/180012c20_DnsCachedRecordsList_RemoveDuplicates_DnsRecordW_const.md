# DnsCachedRecordsList::RemoveDuplicates(_DnsRecordW const *)

- ea: `0x180012c20`
- end: `0x180012fc2`
- name: `?RemoveDuplicates@DnsCachedRecordsList@@QEAAXPEBU_DnsRecordW@@@Z`
- size: `930`
- prototype: `void __fastcall(DnsCachedRecordsList *__hidden this, const struct _DnsRecordW *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003994c`

## callees

- `0x18000cc80`
- `0x180012c20`
- `0x1800132c0`
- `0x1800136a0`
- `0x1800865fc`
- `0x180086700`
- `0x180086b1c`
- `0x180086f24`
- `0x180086fe4`

## import_xrefs

- `DNSAPI!DnsNameCompare_W` at `0x180012d4d`
- `DNSAPI!DnsNameCompare_W` at `0x180012e34`
- `DNSAPI!DnsNameCompare_W` at `0x180012d4d`
- `DNSAPI!DnsNameCompare_W` at `0x180012e34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012dbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012dbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012dd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012dd2`

## string_xrefs

- `0x180012ed7`: `TestComparison1`
- `0x180012f1c`: `TestComparison2`

## pseudocode

```c
void __fastcall DnsCachedRecordsList::RemoveDuplicates(DnsCachedRecordsList *this, const struct _DnsRecordW *a2)
{
  _QWORD *v2; // r14
  _QWORD *v5; // rbx
  _QWORD *v6; // r8
  const struct _DnsRecordW *v7; // rbx
  const struct _DnsRecordW *v8; // r8
  __int64 *v9; // rdi
  unsigned int i; // esi
  __int16 v11; // ax
  _QWORD *v12; // rax
  BOOL v13; // ebp
  const struct _DnsRecordW *j; // rbx
  __int16 v15; // ax
  _QWORD *v16; // rsi
  _QWORD *v17; // rdi
  _QWORD *v18; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v20; // rax

  v2 = *(_QWORD **)this;
  if ( !*(_QWORD *)this )
    return;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 62, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids);
  v5 = (_QWORD *)v2[1];
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_s(1035, 59, WPP_a606ed7dcf923dd2afbb5863f39d97d6_Traceguids, "TestComparison1");
  if ( v5 )
  {
    v6 = 0;
    do
    {
      DnsPrint_Record(this, v5, v6);
      v6 = v5;
      v5 = (_QWORD *)*v5;
    }
    while ( v5 );
  }
  else
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_10;
    WPP_SF_(1035, 60, WPP_a606ed7dcf923dd2afbb5863f39d97d6_Traceguids);
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_(1035, 63, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_s(1035, 59, WPP_a606ed7dcf923dd2afbb5863f39d97d6_Traceguids, "TestComparison2");
  }
LABEL_10:
  if ( a2 )
  {
    v7 = a2;
    v8 = 0;
    do
    {
      DnsPrint_Record(this, v7, v8);
      v8 = v7;
      v7 = v7->pNext;
    }
    while ( v7 );
  }
  else if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_(1035, 60, WPP_a606ed7dcf923dd2afbb5863f39d97d6_Traceguids);
  }
  do
  {
    v9 = (__int64 *)v2[1];
    for ( i = 0; v9; v9 = (__int64 *)*v9 )
    {
      v11 = *((_WORD *)v9 + 8);
      ++i;
      if ( v11 == 12 || v11 == 33 )
      {
        v13 = 0;
        for ( j = a2; j; j = j->pNext )
        {
          v15 = *((_WORD *)v9 + 8);
          if ( v15 == j->wType )
          {
            if ( v15 == 12 )
            {
              v13 = DnsNameCompare_W((PCWSTR)v9[4], j->Data.SOA.pNamePrimaryServer);
              if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                WPP_SF_SS(
                  1035,
                  56,
                  (unsigned int)WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids,
                  v9[4],
                  (__int64)j->Data.SOA.pNamePrimaryServer);
            }
            else if ( v15 == 33 )
            {
              if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                WPP_SF_SS(
                  1035,
                  57,
                  (unsigned int)WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids,
                  v9[4],
                  (__int64)j->Data.SOA.pNamePrimaryServer);
              v13 = DnsNameCompare_W((PCWSTR)v9[4], j->Data.SOA.pNamePrimaryServer);
            }
            if ( v13 )
            {
              if ( i > 1 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                WPP_SF_d(1035, 58, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids, i);
              v16 = (_QWORD *)*v2;
              v17 = (_QWORD *)v2[1];
              if ( g_fVelocityDnsKernelApi )
              {
                Dns_RecordListFree_New(v2[1]);
              }
              else
              {
                if ( (BYTE3(xmmword_1800AB5A0) & 4) != 0 )
                  WPP_SF_q(1050, 12, WPP_8a8073b2d2d83a34ea4a6c85ce67b617_Traceguids, v2[1]);
                if ( v17 )
                {
                  do
                  {
                    v18 = (_QWORD *)*v17;
                    Dns_RecordFree(v17);
                    v17 = v18;
                  }
                  while ( v18 );
                }
              }
              ProcessHeap = g_hProcessHeap;
              if ( !g_hProcessHeap )
              {
                ProcessHeap = GetProcessHeap();
                g_hProcessHeap = ProcessHeap;
              }
              HeapFree(ProcessHeap, 0, v2);
              v2 = v16;
              goto LABEL_39;
            }
          }
        }
      }
    }
    v12 = (_QWORD *)*((_QWORD *)this + 1);
    if ( v12 )
      *v12 = v2;
    else
      *(_QWORD *)this = v2;
    *((_QWORD *)this + 1) = v2;
    v2 = (_QWORD *)*v2;
    ++*((_DWORD *)this + 4);
LABEL_39:
    ;
  }
  while ( v2 );
  v20 = (_QWORD *)*((_QWORD *)this + 1);
  if ( v20 )
    *v20 = 0;
}

```

## disassembly

```asm
0x180012c20  push    r12
0x180012c22  push    r14
0x180012c24  push    r15
0x180012c26  sub     rsp, 40h
0x180012c2a  mov     r14, [rcx]
0x180012c2d  mov     r15, rdx
0x180012c30  mov     r12, rcx
0x180012c33  test    r14, r14
0x180012c36  jz      loc_180012E0A
0x180012c3c  mov     [rsp+58h+arg_0], rbx
0x180012c41  mov     [rsp+58h+arg_8], rbp
0x180012c46  mov     [rsp+58h+arg_10], rsi
0x180012c4b  mov     [rsp+58h+var_20], rdi
0x180012c50  mov     [rsp+58h+var_28], r13
0x180012c55  xor     r13d, r13d
0x180012c58  mov     [rcx], r13
0x180012c5b  mov     [rcx+8], r13
0x180012c5f  mov     [rcx+10h], r13d
0x180012c63  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180012c6a  jnz     loc_180012F61
0x180012c70  mov     rbx, [r14+8]
0x180012c74  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180012c7b  jnz     loc_180012ED2
0x180012c81  test    rbx, rbx
0x180012c84  jz      loc_180012E8C
0x180012c8a  mov     r8, r13
0x180012c8d  mov     rdx, rbx
0x180012c90  call    DnsPrint_Record
0x180012c95  mov     r8, rbx
0x180012c98  mov     rbx, [rbx]
0x180012c9b  test    rbx, rbx
0x180012c9e  jnz     short loc_180012C8D
0x180012ca0  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180012ca7  jnz     loc_180012EF4
0x180012cad  test    r15, r15
0x180012cb0  jz      loc_180012E64
0x180012cb6  mov     rbx, r15
0x180012cb9  mov     r8, r13
0x180012cbc  mov     rdx, rbx
0x180012cbf  call    DnsPrint_Record
0x180012cc4  mov     r8, rbx
0x180012cc7  mov     rbx, [rbx]
0x180012cca  test    rbx, rbx
0x180012ccd  jnz     short loc_180012CBC
0x180012ccf  nop
0x180012cd0  mov     rdi, [r14+8]
0x180012cd4  mov     ebp, r13d
0x180012cd7  mov     esi, r13d
0x180012cda  test    rdi, rdi
0x180012cdd  jz      short loc_180012CFE
0x180012cdf  nop
0x180012ce0  movzx   eax, word ptr [rdi+10h]
0x180012ce4  inc     esi
0x180012ce6  cmp     ax, 0Ch
0x180012cea  jz      short loc_180012D21
0x180012cec  cmp     ax, 21h ; '!'
0x180012cf0  jz      short loc_180012D21
0x180012cf2  mov     rdi, [rdi]
0x180012cf5  test    rdi, rdi
0x180012cf8  jnz     short loc_180012CE0
0x180012cfa  test    ebp, ebp
0x180012cfc  jnz     short loc_180012D66
0x180012cfe  mov     rax, [r12+8]
0x180012d03  test    rax, rax
0x180012d06  jz      loc_180012E4E
0x180012d0c  mov     [rax], r14
0x180012d0f  mov     [r12+8], r14
0x180012d14  mov     r14, [r14]
0x180012d17  inc     dword ptr [r12+10h]
0x180012d1c  jmp     loc_180012DDB
0x180012d21  mov     ebp, r13d
0x180012d24  mov     rbx, r15
0x180012d27  test    rbx, rbx
0x180012d2a  jz      short loc_180012CF2
0x180012d2c  movzx   eax, word ptr [rdi+10h]
0x180012d30  cmp     ax, [rbx+10h]
0x180012d34  jz      short loc_180012D3B
0x180012d36  mov     rbx, [rbx]
0x180012d39  jmp     short loc_180012D27
0x180012d3b  cmp     ax, 0Ch
0x180012d3f  jnz     loc_180012E15
0x180012d45  mov     rdx, [rbx+20h]; pName2
0x180012d49  mov     rcx, [rdi+20h]; pName1
0x180012d4d  call    cs:__imp_DnsNameCompare_W
0x180012d53  mov     ebp, eax
0x180012d55  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180012d5c  jnz     loc_180012F39
0x180012d62  test    ebp, ebp
0x180012d64  jz      short loc_180012D36
0x180012d66  cmp     esi, 1
0x180012d69  jbe     short loc_180012D78
0x180012d6b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180012d72  jnz     loc_180012FA4
0x180012d78  cmp     cs:g_fVelocityDnsKernelApi, r13d
0x180012d7f  mov     rsi, [r14]
0x180012d82  mov     rdi, [r14+8]
0x180012d86  jnz     loc_180012E41
0x180012d8c  test    byte ptr cs:xmmword_1800AB5A0+3, 4
0x180012d93  jnz     loc_180012EB4
0x180012d99  test    rdi, rdi
0x180012d9c  jz      short loc_180012DB1
0x180012d9e  mov     rbx, [rdi]
0x180012da1  mov     rcx, rdi
0x180012da4  call    Dns_RecordFree
0x180012da9  mov     rdi, rbx
0x180012dac  test    rbx, rbx
0x180012daf  jnz     short loc_180012D9E
0x180012db1  mov     rax, cs:g_hProcessHeap
0x180012db8  test    rax, rax
0x180012dbb  jnz     short loc_180012DCA
0x180012dbd  call    cs:__imp_GetProcessHeap
0x180012dc3  mov     cs:g_hProcessHeap, rax
0x180012dca  mov     r8, r14; lpMem
0x180012dcd  xor     edx, edx; dwFlags
0x180012dcf  mov     rcx, rax; hHeap
0x180012dd2  call    cs:__imp_HeapFree
0x180012dd8  mov     r14, rsi
0x180012ddb  test    r14, r14
0x180012dde  jnz     loc_180012CD0
0x180012de4  mov     rax, [r12+8]
0x180012de9  mov     rdi, [rsp+58h+var_20]
0x180012dee  mov     rsi, [rsp+58h+arg_10]
0x180012df3  mov     rbp, [rsp+58h+arg_8]
0x180012df8  mov     rbx, [rsp+58h+arg_0]
0x180012dfd  test    rax, rax
0x180012e00  jz      short loc_180012E05
0x180012e02  mov     [rax], r13
0x180012e05  mov     r13, [rsp+58h+var_28]
0x180012e0a  add     rsp, 40h
0x180012e0e  pop     r15
0x180012e10  pop     r14
0x180012e12  pop     r12
0x180012e14  retn
0x180012e15  cmp     ax, 21h ; '!'
0x180012e19  jnz     loc_180012D62
0x180012e1f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180012e26  jnz     loc_180012F7C
0x180012e2c  mov     rdx, [rbx+20h]; pName2
0x180012e30  mov     rcx, [rdi+20h]; pName1
0x180012e34  call    cs:__imp_DnsNameCompare_W
0x180012e3a  mov     ebp, eax
0x180012e3c  jmp     loc_180012D62
0x180012e41  mov     rcx, rdi
0x180012e44  call    Dns_RecordListFree_New
0x180012e49  jmp     loc_180012DB1
0x180012e4e  mov     [r12], r14
0x180012e52  mov     [r12+8], r14
0x180012e57  mov     r14, [r14]
0x180012e5a  inc     dword ptr [r12+10h]
0x180012e5f  jmp     loc_180012DDB
0x180012e64  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180012e6b  jz      loc_180012CD0
0x180012e71  mov     edx, 3Ch ; '<'
0x180012e76  lea     r8, WPP_a606ed7dcf923dd2afbb5863f39d97d6_Traceguids
0x180012e7d  mov     ecx, 40Bh
0x180012e82  call    WPP_SF_
0x180012e87  jmp     loc_180012CD0
0x180012e8c  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180012e93  jz      loc_180012CAD
0x180012e99  mov     edx, 3Ch ; '<'
0x180012e9e  lea     r8, WPP_a606ed7dcf923dd2afbb5863f39d97d6_Traceguids
0x180012ea5  mov     ecx, 40Bh
0x180012eaa  call    WPP_SF_
0x180012eaf  jmp     loc_180012CA0
0x180012eb4  mov     edx, 0Ch
0x180012eb9  lea     r8, WPP_8a8073b2d2d83a34ea4a6c85ce67b617_Traceguids
0x180012ec0  mov     ecx, 41Ah
0x180012ec5  mov     r9, rdi
0x180012ec8  call    WPP_SF_q
0x180012ecd  jmp     loc_180012D99
0x180012ed2  mov     edx, 3Bh ; ';'
0x180012ed7  lea     r9, aTestcomparison_0; "TestComparison1"
0x180012ede  mov     ecx, 40Bh
0x180012ee3  lea     r8, WPP_a606ed7dcf923dd2afbb5863f39d97d6_Traceguids
0x180012eea  call    WPP_SF_s
0x180012eef  jmp     loc_180012C81
0x180012ef4  mov     edx, 3Fh ; '?'
0x180012ef9  lea     r8, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids
0x180012f00  mov     ecx, 40Bh
0x180012f05  call    WPP_SF_
0x180012f0a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180012f11  jz      loc_180012CAD
0x180012f17  mov     edx, 3Bh ; ';'
0x180012f1c  lea     r9, aTestcomparison; "TestComparison2"
0x180012f23  mov     ecx, 40Bh
0x180012f28  lea     r8, WPP_a606ed7dcf923dd2afbb5863f39d97d6_Traceguids
0x180012f2f  call    WPP_SF_s
0x180012f34  jmp     loc_180012CAD
0x180012f39  mov     r8, [rbx+20h]
0x180012f3d  mov     edx, 38h ; '8'
0x180012f42  mov     r9, [rdi+20h]
0x180012f46  mov     ecx, 40Bh
0x180012f4b  mov     [rsp+58h+var_38], r8
0x180012f50  lea     r8, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids
0x180012f57  call    WPP_SF_SS
0x180012f5c  jmp     loc_180012D62
0x180012f61  mov     edx, 3Eh ; '>'
0x180012f66  lea     r8, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids
0x180012f6d  mov     ecx, 40Bh
0x180012f72  call    WPP_SF_
0x180012f77  jmp     loc_180012C70
0x180012f7c  mov     rax, [rbx+20h]
0x180012f80  lea     r8, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids
0x180012f87  mov     r9, [rdi+20h]
0x180012f8b  mov     edx, 39h ; '9'
0x180012f90  mov     ecx, 40Bh
0x180012f95  mov     [rsp+58h+var_38], rax
0x180012f9a  call    WPP_SF_SS
0x180012f9f  jmp     loc_180012E2C
0x180012fa4  mov     edx, 3Ah ; ':'
0x180012fa9  lea     r8, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids
0x180012fb0  mov     ecx, 40Bh
0x180012fb5  mov     r9d, esi
0x180012fb8  call    WPP_SF_d
0x180012fbd  jmp     loc_180012D78
```
