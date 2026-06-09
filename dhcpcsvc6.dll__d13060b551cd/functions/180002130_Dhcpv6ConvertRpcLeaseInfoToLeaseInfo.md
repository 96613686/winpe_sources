# Dhcpv6ConvertRpcLeaseInfoToLeaseInfo

- ea: `0x180002130`
- end: `0x180002242`
- name: `Dhcpv6ConvertRpcLeaseInfoToLeaseInfo`
- size: `274`
- prototype: `__int64 __fastcall(__int64, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800016f0`

## callees

- `0x180002130`
- `0x1800082b0`

## pseudocode

```c
__int64 __fastcall Dhcpv6ConvertRpcLeaseInfoToLeaseInfo(__int64 a1, unsigned int *a2)
{
  char v4; // cl
  __int64 result; // rax
  __int64 v6; // r8
  __int16 v7; // cx
  __int64 v8; // rcx
  unsigned int *v9; // rdx

  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_(a1, 56, WPP_cb48999f8e5838f952918348529d50de_Traceguids);
  v4 = *((_BYTE *)a2 + 84);
  *(_BYTE *)(a1 + 120) = v4;
  *(_BYTE *)(a1 + 176) = *((_BYTE *)a2 + 124);
  result = *a2;
  *(_DWORD *)a1 = result;
  *(_OWORD *)(a1 + 177) = *(_OWORD *)((char *)a2 + 125);
  if ( v4 )
  {
    v6 = 0;
    *(_DWORD *)(a1 + 8) = a2[1];
    *(_WORD *)(a1 + 112) = *((_WORD *)a2 + 40);
    *(_QWORD *)(a1 + 16) = a2[2];
    *(_QWORD *)(a1 + 24) = a2[3];
    result = 0;
    v7 = *((_WORD *)a2 + 40);
    *(_WORD *)(a1 + 112) = v7;
    if ( v7 )
    {
      do
      {
        v8 = a1 + 40 * v6;
        v9 = &a2[8 * (unsigned int)v6];
        v6 = (unsigned int)(v6 + 1);
        *(_QWORD *)(v8 + 64) = v9[11];
        *(_QWORD *)(v8 + 56) = v9[10];
        *(_DWORD *)(v8 + 48) = v9[8];
        *(_DWORD *)(v8 + 52) = v9[9];
        *(_OWORD *)(v8 + 32) = *((_OWORD *)v9 + 1);
        result = *(unsigned __int16 *)(a1 + 112);
      }
      while ( (unsigned int)v6 < (unsigned int)result );
    }
  }
  if ( *(_BYTE *)(a1 + 176) )
  {
    *(_DWORD *)(a1 + 128) = a2[22];
    *(_QWORD *)(a1 + 168) = a2[30];
    *(_QWORD *)(a1 + 160) = a2[29];
    *(_DWORD *)(a1 + 152) = a2[27];
    result = a2[28];
    *(_DWORD *)(a1 + 156) = result;
    *(_OWORD *)(a1 + 136) = *(_OWORD *)(a2 + 23);
  }
  return result;
}

```

## disassembly

```asm
0x180002130  mov     [rsp+arg_0], rbx
0x180002135  push    rdi
0x180002136  sub     rsp, 20h
0x18000213a  mov     rdi, rdx
0x18000213d  mov     rbx, rcx
0x180002140  test    byte ptr cs:xmmword_18000F160, 10h
0x180002147  jz      short loc_18000215A
0x180002149  mov     edx, 38h ; '8'
0x18000214e  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180002155  call    WPP_SF_
0x18000215a  movzx   ecx, byte ptr [rdi+54h]
0x18000215e  mov     [rbx+78h], cl
0x180002161  movzx   eax, byte ptr [rdi+7Ch]
0x180002165  mov     [rbx+0B0h], al
0x18000216b  mov     eax, [rdi]
0x18000216d  mov     [rbx], eax
0x18000216f  movups  xmm0, xmmword ptr [rdi+7Dh]
0x180002173  movups  xmmword ptr [rbx+0B1h], xmm0
0x18000217a  test    cl, cl
0x18000217c  jnz     short loc_1800021CE
0x18000217e  cmp     byte ptr [rbx+0B0h], 0
0x180002185  jnz     short loc_180002192
0x180002187  mov     rbx, [rsp+28h+arg_0]
0x18000218c  add     rsp, 20h
0x180002190  pop     rdi
0x180002191  retn
0x180002192  mov     eax, [rdi+58h]
0x180002195  mov     [rbx+80h], eax
0x18000219b  mov     eax, [rdi+78h]
0x18000219e  mov     [rbx+0A8h], rax
0x1800021a5  mov     eax, [rdi+74h]
0x1800021a8  mov     [rbx+0A0h], rax
0x1800021af  mov     eax, [rdi+6Ch]
0x1800021b2  mov     [rbx+98h], eax
0x1800021b8  mov     eax, [rdi+70h]
0x1800021bb  mov     [rbx+9Ch], eax
0x1800021c1  movups  xmm0, xmmword ptr [rdi+5Ch]
0x1800021c5  movups  xmmword ptr [rbx+88h], xmm0
0x1800021cc  jmp     short loc_180002187
0x1800021ce  mov     eax, [rdi+4]
0x1800021d1  xor     r8d, r8d
0x1800021d4  mov     [rbx+8], eax
0x1800021d7  movzx   eax, word ptr [rdi+50h]
0x1800021db  mov     [rbx+70h], ax
0x1800021df  mov     eax, [rdi+8]
0x1800021e2  mov     [rbx+10h], rax
0x1800021e6  mov     eax, [rdi+0Ch]
0x1800021e9  mov     [rbx+18h], rax
0x1800021ed  xor     eax, eax
0x1800021ef  movzx   ecx, word ptr [rdi+50h]
0x1800021f3  mov     [rbx+70h], cx
0x1800021f7  cmp     ax, cx
0x1800021fa  jnb     short loc_18000217E
0x1800021fc  lea     rax, [r8+r8*4]
0x180002200  mov     edx, r8d
0x180002203  lea     rcx, [rbx+rax*8]
0x180002207  shl     rdx, 5
0x18000220b  add     rdx, rdi
0x18000220e  inc     r8d
0x180002211  mov     eax, [rdx+2Ch]
0x180002214  mov     [rcx+40h], rax
0x180002218  mov     eax, [rdx+28h]
0x18000221b  mov     [rcx+38h], rax
0x18000221f  mov     eax, [rdx+20h]
0x180002222  mov     [rcx+30h], eax
0x180002225  mov     eax, [rdx+24h]
0x180002228  mov     [rcx+34h], eax
0x18000222b  movups  xmm0, xmmword ptr [rdx+10h]
0x18000222f  movups  xmmword ptr [rcx+20h], xmm0
0x180002233  movzx   eax, word ptr [rbx+70h]
0x180002237  cmp     r8d, eax
0x18000223a  jnb     loc_18000217E
0x180002240  jmp     short loc_1800021FC
```
