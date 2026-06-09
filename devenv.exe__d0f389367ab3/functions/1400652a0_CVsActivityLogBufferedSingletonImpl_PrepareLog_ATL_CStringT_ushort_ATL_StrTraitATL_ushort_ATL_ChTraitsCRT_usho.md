# CVsActivityLogBufferedSingletonImpl::PrepareLog(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,bool)

- ea: `0x1400652a0`
- end: `0x14006535d`
- name: `?PrepareLog@CVsActivityLogBufferedSingletonImpl@@AEAAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@Z`
- size: `189`
- prototype: `__int64 __fastcall(CVsActivityLogBufferedSingletonImpl *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140065360`

## callees

- `0x14002fa90`
- `0x140064fc0`
- `0x1400652a0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400652d3`
- `KERNEL32!EnterCriticalSection` at `0x1400652d3`
- `KERNEL32!LeaveCriticalSection` at `0x140065339`
- `KERNEL32!LeaveCriticalSection` at `0x140065339`

## string_xrefs

- `0x1400652e3`: `<?xml version="1.0" encoding="utf-16"?>\n<?xml-stylesheet type="text/xsl" href="#stylesheet"?>\n<activity>\n	<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" id="stylesheet" xml:id="stylesheet">\n		<xsl:output method="html"  encoding="utf-16"/>\n		<!-- Don't reprint text nodes within the xsl:stylesheet node -->\n		<xsl:template match="text()"/>\n		<xsl:template match="activity">\n			<head>\n				<title>Activity Monitor Log</title>\n				<style type="text/css`

## pseudocode

```c

```
